<template>
  <Header />
  <div class="container" role="main">
    <div class="filters-container">
      <h3 class="filter-title"> Web Sites </h3>
      <div class="filter-boxes appearance-none checked:bg-blue-500">
    <label class="flex">
<input class="ml-2 mr-1 mb-1 mt-1 inline-block" data-id="{{inputDataId}}" type="checkbox" >
<span class="text-sm inline-block">
 sdfsd fsd fsd fsdfds fsdf sdf s fsdfsdf
</span>
</label>      <input type="checkbox" name="fruit" value="Orange"> Orange
      <input type="checkbox" name="fruit" value="Banana"> Banana
      <input type="checkbox" name="fruit" value="Apple"> Apple
      <input type="checkbox" name="fruit" value="Orange"> Orange
      <input type="checkbox" name="fruit" value="Banana"> Banana
      <input type="checkbox" name="fruit" value="Apple"> Apple
      <input type="checkbox" name="fruit" value="Orange"> Orange
      <input type="checkbox" name="fruit" value="Banana"> Banana
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
  @apply flex flex-col lg:flex-row
   lg:space-x-8 max-w-max
    pr-8 pl-28 justify-center
}

.filter-title{
  @apply font-sans text-xl
  mx-auto font-bold
}

.filter-boxes{
  @apply flex flex-col
  font-sans items-start font-medium
  border-solid text-lg lg:w-[280px]
  rounded-md border-2 border-black;
}
.filters-container{
  @apply
  flex flex-col min-w-min
  content-center shrink mx-auto
   w-1/6 md:w-2/6 lg:w-3/6
}

.btn {
    @apply flex bg-black
     m-5 px-8 py-2 w-max mx-auto
    cursor-pointer rounded-md border-none
    text-sm text-left font-sans text-white
}
</script>

.results-container {
 @apply flex flex-col content-center pl-40 pt-[70px]
}

.contest-tile{
  @apply flex flex-col space-y-0
  font-sans text-xl font-normal
  rounded-md border-2 border-black
  border-solid mx-auto items-start
  mb-4 lg:w-[600px] leading-normal pl-4
  /* w-[40%] md:w-[50%] lg:max-w-[60%] */
}
</style>
