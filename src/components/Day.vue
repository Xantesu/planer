<template>
    <div class="day">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "Day.vue"
    }
</script>

<style scoped>
    .day {
        flex: 1;
        flex-basis: auto;
        overflow: hidden;
        transition: width .3s linear;
        /*text-align: center;*/
        display: flex;
        width: 0%;
        align-items: center;
        justify-content: center;
        background-color: #ff9594;
    }

    .day p {
    }

    .day:hover {
    }
</style>
