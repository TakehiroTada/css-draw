<template>
  <div class="layout__index">
    <div class="layout__index__canvas">
      <gear-clock-base />
      <gear-clock-mini
        v-for="(clockMini, index) in clockMinis"
        :key="index"
        :size="clockMini.size"
        :x-point="clockMini.xPoint"
        :y-point="clockMini.yPoint"
      />
    </div>
  </div>
</template>

<script>
import GearClockBase from '~/components/GearClockBase.vue'
import GearClockMini from '~/components/GearClockMini.vue'

export default {
  components: {
    GearClockBase,
    GearClockMini
  },
  data: () => ({
    clockMinis: [
      {
        size: 30,
        xPoint: 23,
        yPoint: 13
      },
      {
        size: 18,
        xPoint: 46,
        yPoint: 32
      },
      {
        size: 23,
        xPoint: 17,
        yPoint: 49
      },
      {
        size: 36,
        xPoint: 45,
        yPoint: 48
      },
      {
        size: 20,
        xPoint: 64,
        yPoint: 24
      }
    ]
  })
}
</script>

<style lang="scss" scoped>
.layout__index {
  display: flex;
  width: 100%;
  height: 100%;
}
.layout__index__canvas {
  position: relative;
  width: 1000px;
  height: 1000px;
  border: 1px solid white;
  background-color: black;
}
</style>
