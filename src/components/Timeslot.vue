<template>
    <div class="time">
        <slot></slot>
        <app-modul v-for="day in days">
            <p class="name">{{ subjects[day-1].name }}</p>
            <p class="type">{{ subjects[day-1].type }}</p>
        </app-modul>
    </div>
</template>

<script>
    import Modul from './Modul';
    export default {
        data(){
            return {
                days: 5,
            };
        },
        components: {
            appModul: Modul,
        },
        props: ['subjects'],
    }
</script>

<style scoped>
    p {
        font-family: Roboto;
        margin: auto;
        padding: 1em 1em .1em 1em;
    }
    .type {
        padding-top: .1em;
        padding-left: 1.2em;
        color: #595959;
        font-size: .9em;
        line-height: 100%;
        margin: 0;
    }


    .time {
        display: flex;
        flex: 1;
        flex-basis: auto;
        overflow: hidden;
        height: 0%;
        box-sizing: border-box;
        transition: .2s linear;
    }
</style>