<template>
    <div class="contest-tile">
        <a :href=url class="font-bold text-lg">{{name}}</a>
        <p class="m-0"> Start time: {{start_time}} </p>
        <p>End time: {{end_time}} </p>
        <p>Duration: {{durationInHours}} </p>
    </div>
</template>

<script>
    import { format, formatDuration, intervalToDuration } from 'date-fns'

    export default {
        name: "Contest-Tile",
        data() {
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
            durationInHours() {
                const interval = intervalToDuration({
                    start: 0,
                    end: Number(this.duration)
                })
                return formatDuration(interval, {
                    format: ['hours', 'minutes']
                })
            }
        },
        methods: {
            formatDateTime(dateTimeString) {
                return format(Date.parse(dateTimeString), 'dd MMM y | HH:MM')
            }
        }
    }
</script>

<style scoped lang="postcss">
    .span {
        @apply font-bold
    }

    .contest-tile {
        @apply flex flex-col items-start
        rounded-md border-2 border-black border-solid
        mx-auto mb-4 w-[340px] pl-4 space-y-0
        text-base lg:text-xl lg:font-normal text-black font-sans

    }
</style>