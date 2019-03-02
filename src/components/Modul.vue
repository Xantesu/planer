<template>
   <div class="module">
      <slot></slot>
   </div>
</template>

<script>
    export default {
        name: "Modul.vue"
    }
</script>

<style scoped>
   .module {
      flex: 1;
      flex-basis: auto;
      overflow: hidden;
      width: 0%;
      /*border: 1px solid black;*/
      background-color: #f3f3f3;
      transition: width .2s linear;
       border: .1em dotted lightblue;
   }

   .module:hover {
      background-color: #e0f1ff;
   }
</style>