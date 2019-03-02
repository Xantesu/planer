<template>
    <div class="week">
        <app-day v-for="day in days"><p>{{ day }}</p></app-day>
    </div>
</template>

<script>
    import Day from './Day';
    export default {
        data(){
            return {
                days: [
                    'Monday',
                    'Tuesday',
                    'Wednesday',
                    'Thursday',
                    'Friday',
                ],
            };
        },
        components: {
            appDay: Day,
        },
    }
</script>

<style scoped>
    p {
        font-family: "Roboto";
        font-weight: bolder;
        font-size: 1em;
    }
    .week {
        display: flex;
        flex: 1;
        flex-basis: auto;
        overflow: hidden;
        height: 0%;
        box-sizing: border-box;
        transition: .3s ease-out;
        justify-self: start;
    }
</style>
