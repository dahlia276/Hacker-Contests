<template>
  <Header />
  <div class="container" role="main">
    <div class="filters-container">
      <h3 class="filter-title"> Web Sites </h3>
      <div class="filter-boxes appearance-none checked:bg-blue-500">
    <label class="flex">
<input class="ml-2 mr-1 mb-1 mt-1 inline-block" data-id="{{inputDataId}}" type="checkbox" >
<span class="text-sm inline-block">
 sdfsd fsd fsd fsdfds fsdf 
</span>
</label>  
<label class="flex">
<input class="ml-2 mr-1 mb-1 mt-1 inline-block" data-id="{{inputDataId}}" type="checkbox" >
<span class="text-sm inline-block">
 sdfsd fsd fsd fsdfds fsdf 
</span>
</label>      
<label class="flex">
<input class="ml-2 mr-1 mb-1 mt-1 inline-block" data-id="{{inputDataId}}" type="checkbox" >
<span class="text-sm inline-block">
 sdfsd fsd fsd fsdfds fsdf 
</span>
</label>      
<label class="flex">
<input class="ml-2 mr-1 mb-1 mt-1 inline-block" data-id="{{inputDataId}}" type="checkbox" >
<span class="text-sm inline-block">
 sdfsd fsd fsd fsdfds fsdf 
</span>
</label>      
<label class="flex">
<input class="ml-2 mr-1 mb-1 mt-1 inline-block" data-id="{{inputDataId}}" type="checkbox" >
<span class="text-sm inline-block">
 sdfsd fsd fsd fsdfds fsdf 
</span>
</label>      
<label class="flex">
<input class="ml-2 mr-1 mb-1 mt-1 inline-block" data-id="{{inputDataId}}" type="checkbox" >
<span class="text-sm inline-block">
 sdfsd fsd fsd fsdfds fsdf 
</span>
</label>      
<label class="flex">
<input class="ml-2 mr-1 mb-1 mt-1 inline-block" data-id="{{inputDataId}}" type="checkbox" >
<span class="text-sm inline-block">
 sdfsd fsd fsd fsdfds fsdf 
</span>
</label>      
      </div>
        <button class="btn"> Show Contests</button>
       </div>
       <!-- <img src="./src/assets/circles-menu-3.gif" alt="loading icon"> -->
       <ContestsContainer :contests="this.contests"/>
  </div>
</template>

<script>
import Header from '@/components/Header';
import ContestsContainer from "@/components/ContestsContainer.vue"

export default {
  components: {
    Header,
   ContestsContainer,
  },
   props: {},
    data() {
    return {
      contests: []
    }
  },
  methods:{
    async getContests() {
      try {
      const res = await fetch('https://kontests.net/api/v1/all')
      this.contests = await res.json()
      }
      catch(error){
        alert("Sorry, The content you're looking for is currently unavailable")
      }
    },
  },
  created () {
    this.getContests()
  }
  };

</script>

<style scoped lang="postcss">

.container{
  @apply flex flex-col md:flex-row md:space-x-16
   lg:space-x-8 max-w-max
   justify-center mx-auto
    /* pr-8 pl-28  */
}

.filter-title{
  @apply font-sans text-xl
  mx-auto 
}

.filter-boxes{
  @apply flex flex-col
  font-sans items-center pr-4 pl-4 md:pr-0 md:pl-0 pt-4 pb-4 font-medium
  border-solid text-lg lg:w-[280px] md:w-[300px]
  rounded-md border-2 border-black;
}
.filters-container{
  @apply
  flex flex-col min-w-min
  content-center shrink mx-auto
   /* w-1/6 md:w-2/6 lg:w-3/6 */
}

.btn {
    @apply flex bg-black
     m-5 px-8 py-2 w-max mx-auto
    cursor-pointer rounded-md border-none
    text-sm text-left font-sans text-white
}
</style>
