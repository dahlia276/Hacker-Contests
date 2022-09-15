<template>
  <Header />
  <div class="container" role="main">
      <SitesContainer @toggleSite="(toggledSiteName) => this.toggleSite(toggledSiteName)"/>
       <ContestsContainer :contests="this.contests"/>
  </div>
</template>

<script>
import Header from '@/components/Header';
import ContestsContainer from "@/components/ContestsContainer.vue"
import SitesContainer from '@/components/SitesContainer.vue'

export default {
  components: {
    Header,
   ContestsContainer,
   SitesContainer
  },
   props: {},
    data() {
    return {
      contests: [],
      checkedSites: []
    }
  },
  methods:{
    async getAllContests() {
      try {
      const res = await fetch('https://kontests.net/api/v1/all')
      this.contests = await res.json()
      }
      catch(error){
        alert("Sorry, The content you're looking for is currently unavailable")
      }
    },
    async updateContests(){
      await this.getAllContests();
      this.contests = this.contests.filter(contest => this.checkedSites.includes(contest.site))
    },
     toggleSite(siteName) {
      var index = this.checkedSites.indexOf(siteName);

      if (index === -1) {
          this.checkedSites.push(siteName);
      } else {
          this.checkedSites.splice(index, 1);
      }
      this.updateContests()
    }
  },
  created () {
    this.getAllContests()
  }
  };

</script>

<style scoped lang="postcss">

.container{
  @apply flex flex-col md:flex-row md:space-x-16
   lg:space-x-8 max-w-max
   justify-center mx-auto
}
</style>
