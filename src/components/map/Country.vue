<script setup>
  import Base from "@/components/chart/Base.vue";
  import ChinaWithRegion from '@/mock/ChinaWithRegion.json'


  console.log(ChinaWithRegion)

</script>

<template>
  <Base :map-features="ChinaWithRegion"></Base>
</template>

<style scoped lang="scss">

</style>