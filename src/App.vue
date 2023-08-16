<script setup lang="ts">
import Country from "./components/map/Country.vue";
</script>

<template>
  <div class="map-chart-app">
    <Country></Country>
  </div>
</template>

<style lang="scss">
.map-chart-app {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
}
</style>
