<template>
  <div class="fullscreen">
  </div>
</template>

<script>
    export default {
        name: "Background"
    }
</script>

<style scoped>
  .fullscreen {
    background: url('../static/mountains_background.jpg') center center / cover no-repeat;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    z-index: -101;
  }



</style>
