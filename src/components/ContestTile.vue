<template>
    <div class="tile-text">
        <a :href=url class="font-bold text-lg">{{name}}</a>
        <p class="m-0">  Start time:  {{start_time}} </p>
        <p>End time: {{end_time}} </p>
        <p>Duration: {{durationInHours}} </p>
    </div>
</template>

<script>
import { format, formatDuration } from 'date-fns'

export default {
    name: "Contest-Tile",
    data(){
        return {
            url: this.contest.url,
            name: this.contest.name,
            start_time: this.formatDateTime(this.contest.start_time),
            end_time: this.formatDateTime(this.contest.end_time),
            duration: this.contest.duration
        }
    },
    props: {
    contest: Object
    },
    computed: {
        durationInHours(){
            return formatDuration({seconds: Number(this.duration)})
        }
    },
    methods: {
        formatDateTime(dateTimeString) {
            return format(Date.parse(dateTimeString),'dd MMM y | HH:MM')
        }
    }
}
</script>

<style scoped lang="postcss">

.span{
    @apply font-bold
}
.tile-text{
    @apply flex flex-col
    font-sans items-start 
     text-base lg:text-xl lg:font-normal
     text-black space-y-0 
}
</style>