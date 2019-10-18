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

<style lang="scss">
.layout__index {
  display: flex;
  background-color: black;
}
.layout__index__canvas {
  border: 1px solid white;
}
</style>
