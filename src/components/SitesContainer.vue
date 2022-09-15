<template>
     <div class="sites-container">
        <h3 class="sites-title"> Web Sites </h3>
        <div v-for="site in sites" :key="site.id" class="site-boxes appearance-none checked:bg-blue-500">
          <SiteTile :site="site" @toggleSite="(toggledSite) => $emit('toggleSite',toggledSite)"/>
        </div>
        <button class="btn"> Show Contests</button>
      </div>
</template>

<script>
import SiteTile from '@/components/SiteTile.vue'

export default{
    components: {SiteTile},
     data() {
    return {
      sites: []
    }
  },
  methods:{
    async getSites() {
      try {
        const res = await fetch('https://kontests.net/api/v1/sites')
        const original_sites = await res.json()
        this.sites  = original_sites.map(function(site) {
                return {
                    name: site[0],
                    id: site[1],
                    url: site[2]
                }
            })
        }
      catch(error){
        console.log(error)
      }
    },
  },
  created () {
    this.getSites()
  }
}
</script>

<style scoped lang="postcss">
.sites-title{
  @apply font-sans text-xl
  mx-auto
}

.site-boxes{
  @apply flex flex-col
  font-sans items-center pr-4 pl-4 md:pr-0 md:pl-0 pt-4 pb-4 font-medium
  border-solid text-lg lg:w-[280px] md:w-[300px]
  rounded-md border-2 border-black;
}
.sites-container{
  @apply
  flex flex-col min-w-min
  content-center shrink mx-auto
}

.btn {
    @apply flex bg-black
     m-5 px-8 py-2 w-max mx-auto
    cursor-pointer rounded-md border-none
    text-sm text-left font-sans text-white
}
</style>
