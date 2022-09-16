<template>
  <Header />
  <div class="container" role="main">
    <SitesContainer @toggleSite="this.toggleSite" @initSites="this.initSites" />
    <ContestsContainer :contests="this.contests" :checkedSites="this.checkedSites" />
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
    methods: {
      async getAllContests() {
        try {
          const res = await fetch('https://kontests.net/api/v1/all')
          this.contests = await res.json()
        } catch (error) {
          alert("Sorry, The content you're looking for is currently unavailable")
        }
      },
      toggleSite(siteName) {
        var index = this.checkedSites.indexOf(siteName);

        if (index === -1) {
          this.checkedSites.push(siteName);
        } else {
          this.checkedSites.splice(index, 1);
        }
      },
      initSites(siteNames) {
        this.checkedSites = siteNames
      }
    },
    created() {
      this.getAllContests()
    }
  };
</script>

<style scoped lang="postcss">
  .container {
    @apply flex flex-col md:flex-row
     justify-center mx-auto
     md:space-x-16 lg:space-x-8 max-w-max
  }
</style>