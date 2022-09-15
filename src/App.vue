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
       <div class="results-container"  >
           <div class="contest-tile">
              <a class="contest-title">Contest 1</a>
              <p class="contest-start-date m-0">Start time: 29.10.2022 </p>
              <p class="contest-end-date">End time: 30.10.2022 </p>
              <p class="contest-duration">Duration: 3 hours </p>
            </div>
            <div class="contest-tile">
              <a class="contest-title">Contest 1</a>
              <p class="contest-start-date m-0">Start time: 29.10.2022 </p>
              <p class="contest-end-date">End time: 30.10.2022 </p>
              <p class="contest-duration">Duration: 3 hours </p>
            </div>
            <div class="contest-tile">
              <a class="contest-title">Contest 1</a>
              <p class="contest-start-date m-0">Start time: 29.10.2022 </p>
              <p class="contest-end-date">End time: 30.10.2022 </p>
              <p class="contest-duration">Duration: 3 hours </p>
            </div>
            <div class="contest-tile">
              <a class="contest-title" href="#">Contest 1</a>
              <p class="contest-start-date m-0">Start time: 29.10.2022 </p>
              <p class="contest-end-date">End time: 30.10.2022 </p>
              <p class="contest-duration">Duration: 3 hours </p>
            </div>
        </div>
  </div>
</template>

<script>
import Header from '@/components/Header';

export default {
  components: {
    Header,
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
  mx-auto font-bold
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

.results-container {
 @apply flex flex-col content-center lg:pl-40 pt-[50px] lg:pt-[70px]
}

.contest-tile{
  @apply flex flex-col space-y-0
  font-sans text-base lg:text-xl lg:font-normal
  rounded-md border-2 border-black
  border-solid mx-auto items-start
  mb-4 w-[340px]  leading-normal pl-4
  /* w-[40%] md:w-[50%] lg:max-w-[60%] */
}
</style>
