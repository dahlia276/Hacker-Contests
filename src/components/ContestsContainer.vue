<template>
     <div class="results-container "  >
           <div v-for= "contest in contests" :key="contest.url" class="contest-tile">
              <ContestTile :contest=contest />
            </div>
        </div>
</template>

<script>
import ContestTile from './ContestTile.vue'

export default {
  components: { ContestTile },
    name: "Contests-Container",
    props: {
    contests: Array
}
}

</script>


<style scoped lang="postcss">
.results-container {
 @apply flex flex-col content-center lg:pl-40 pt-[50px] lg:pt-[70px]
}
.contest-tile{
  @apply flex flex-col 
  rounded-md border-2 border-black 
  border-solid mx-auto items-start
  mb-4 w-[340px] pl-4
  /* w-[40%] md:w-[50%] lg:max-w-[60%] */
}
</style>