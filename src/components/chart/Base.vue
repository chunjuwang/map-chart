<script setup>
  import { onBeforeMount, onMounted, onBeforeUnmount, getCurrentInstance } from 'vue'
  import * as echarts from 'echarts'

  const props = defineProps({
    className: {
      type: String,
      default: () => ''
    },
    width: {
      type: String,
      default: () => '100%'
    },
    height: {
      type: String,
      default: () => '100%'
    },
    mapFeatures: {
      type: Object,
      require: true
    }
  })

  echarts.registerMap('ChinaWithRegion', props.mapFeatures)

  let chartInstance = null

  const initChart = () => {
    const { ctx: { $el } } = getCurrentInstance()

    chartInstance || (chartInstance = echarts.init($el))

    chartInstance.setOption({
      geo: {
        map: 'ChinaWithRegion',
        zoom: 1,
        roam: true,
        center: [109.00853, 34.11078],
        label: {
          show: true,
          color: 'rgba(255,255,255,0.2)',
        },
        itemStyle: {
          normal: {
            areaColor: '#080b1a',
            borderColor: 'rgba(0,116,255,0.2)',
            borderWidth: 2,
            borderType: 'dashed',
          },
          emphasis: {
            areaColor: '#4f6ee9',
            color: 'rgba(255,255,255,0.8)',
          },
        },
      },
    })
  }

  const setOption = () => {

  }

  onMounted(() => {
    initChart()
  })

  onBeforeMount(() => {
    chartInstance && chartInstance.dispose()
  })
</script>

<template>
  <div :class="className" :style="{ width, height }"></div>
</template>

<style scoped lang="scss">

</style>