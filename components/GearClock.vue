<template>
  <div class="layout__gear-clock">
    <div class="layout__gear-clock__large-circle"></div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.layout__gear-clock {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.layout__gear-clock__large-circle {
  display: flex;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  /* 背景色のグラデーション */
  background: linear-gradient(150deg, #985f2a, #a08435);
}
</style>
