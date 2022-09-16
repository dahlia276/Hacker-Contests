<template>
  <div class="sites-container">
    <h3 class="sites-title"> Web Sites </h3>
    <div v-for="site in sites" :key="site.id" class="site-boxes appearance-none checked:bg-blue-500">
      <SiteTile :site="site" @toggleSite="(toggledSite) => $emit('toggleSite',toggledSite)" />
    </div>
  </div>
</template>

<script>
  import SiteTile from '@/components/SiteTile.vue'

  export default {
    components: {
      SiteTile
    },
    data() {
      return {
        sites: []
      }
    },
    methods: {
      async getSites() {
        try {
          const res = await fetch('https://kontests.net/api/v1/sites')
          const original_sites = await res.json()
          this.sites = original_sites.map(function (site) {
            return {
              name: site[0],
              id: site[1],
              url: site[2]
            }
          })

          const siteNames = this.sites.map(function (site) {
            return site.name
          })
          this.$emit('initSites', siteNames)
        } catch (error) {
          console.log(error)
        }
      },
    },
    created() {
      this.getSites()
    }
  }
</script>

<style scoped lang="postcss">
  .sites-title {
    @apply font-sans text-xl mx-auto
  }

  .site-boxes {
    @apply flex flex-col items-center
    font-sans font-medium text-lg
    pr-4 pl-4 mb-[15px] pt-4 pb-4
    border-solid rounded-md border-2 border-black
    md:pr-0 md:pl-0 lg:w-[280px] md:w-[300px]
  }

  .sites-container {
    @apply flex flex-col min-w-min content-center shrink mx-auto
  }
</style>