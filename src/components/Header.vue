<template>
    <header>
        <i class=" fa-solid fa-robot fa-4x"></i>
        <h1 class="title">
            Hacker Contests
        </h1>
    </header>
</template>

<script>
    export default {
        name: 'Hacker-Header',
    }
</script>

<style scoped lang="postcss">
    header {
        @apply bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 p-4 mb-10 rounded-lg
    }

    .title {
        @apply font-sans text-center text-white lg:text-8xl md:text-6xl text-3xl font-bold
    }

    .fa-robot {
        @apply bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 rounded-lg text-white
    }
</style>