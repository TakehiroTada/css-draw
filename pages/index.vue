<template>
  <div class="layout__index">
    <div class="layout__index__canvas">
      <gear-clock />
    </div>
  </div>
</template>

<script>
import GearClock from '~/components/GearClock.vue'

export default {
  components: {
    GearClock
  }
}
</script>

<style lang="scss" scoped>
.layout__index {
  display: flex;
  width: 100%;
  height: 100%;
}
.layout__index__canvas {
  width: 1000px;
  height: 1000px;
  border: 1px solid white;
  background-color: black;
}
</style>
