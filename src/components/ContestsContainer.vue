<template>
  <div class="results-container ">
    <div v-for="contest in contests" :key="contest.url">
      <ContestTile v-if="checkedSites.includes(contest.site)" :contest=contest />
    </div>
  </div>
</template>

<script>
  import ContestTile from './ContestTile.vue'

  export default {
    components: {
      ContestTile
    },
    name: "Contests-Container",
    props: {
      contests: Array,
      checkedSites: Array
    }
  }
</script>

<style scoped lang="postcss">
  .results-container {
    @apply flex flex-col content-center
     lg:pl-40 pt-[50px] lg:pt-[70px]
  }
</style>