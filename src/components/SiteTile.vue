<template>
    <label class="flex">
        <input class="ml-2 mr-1 mb-1 mt-1 inline-block" checked @change="$emit('toggleSite', site.name)" value=site.name id=site.id type="checkbox" >
        <span class="text-sm inline-block">
            {{site.name}}
        </span>
        </label>
</template>

<script>
export default{
    components: {},
    props: {
        site: Object
    }
}
</script>
