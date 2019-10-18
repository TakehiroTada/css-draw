<template>
  <div class="layout__gear-clock">
    <!-- 外側のギザギザ用 -->
    <div class="layout__gear-clock__large-circle">
      <!-- 中央の扇型用 -->
      <div class="layout__gear-clock__middle-circle">
        <!-- 中央の小さな円用 -->
        <div class="layout__gear-clock__small-circle"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.layout__gear-clock {
  /* position: relative; */
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.layout__gear-clock__large-circle {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  /* 背景色のグラデーション */
  background: linear-gradient(150deg, #985f2a, #a08435);
}
.layout__gear-clock__middle-circle {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 88%;
  height: 88%;
  border-radius: 50%;
  background: black;
}
.layout__gear-clock__small-circle {
  width: 18%;
  height: 18%;
  border-radius: 50%;
  background: linear-gradient(150deg, #985f2a, #a08435);
}
</style>
