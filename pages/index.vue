<template>
  <div class="layout__index">
    <div class="layout__index__canvas">
      <gear-clock-base />
      <div v-for="(clockMini, index) in clockMinis" :key="index">
        <gear-clock-mini-left
          v-if="index % 2 === 0"
          :size="clockMini.size"
          :x-point="clockMini.xPoint"
          :y-point="clockMini.yPoint"
        />
        <gear-clock-mini-right
          v-else
          :size="clockMini.size"
          :x-point="clockMini.xPoint"
          :y-point="clockMini.yPoint"
        />
      </div>
    </div>
  </div>
</template>

<script>
import GearClockBase from '~/components/GearClockBase.vue'
import GearClockMiniLeft from '~/components/GearClockMiniLeft.vue'
import GearClockMiniRight from '~/components/GearClockMiniRight.vue'

export default {
  components: {
    GearClockBase,
    GearClockMiniLeft,
    GearClockMiniRight
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
