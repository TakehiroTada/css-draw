<template>
  <div class="layout__gear-clock" :style="clockSize">
    <!-- 外側のギザギザ用 -->
    <div class="layout__gear-clock__large-circle">
      <!-- 中央の扇型用 -->
      <div class="layout__gear-clock__middle-circle">
        <!-- 中央の小さな円用 -->
        <div class="layout__gear-clock__small-circle">
          <div class="layout__gear-clock__small-circle__border-top" />
          <div class="layout__gear-clock__small-circle__border-bottom" />
          <div class="layout__gear-clock__small-circle__border-left" />
          <div class="layout__gear-clock__small-circle__border-right" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  computed: {
    widthSize() {
      const size = window.innerWidth <= 1000 ? window.innerWidth : 1000
      return size + 'px'
    },
    clockSize() {
      return {
        width: this.widthSize,
        height: this.widthSize
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.layout__gear-clock {
  /* position: relative; */
  /* width: 800px;
  height: 800px; */
  display: flex;
  justify-content: center;
  align-items: center;
}
.layout__gear-clock__large-circle {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 80%;
  height: 80%;
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
  position: relative;
  display: flex;
  width: 18%;
  height: 18%;
  border-radius: 50%;
  background: linear-gradient(150deg, #985f2a, #a08435);

  &__border-top {
    position: absolute;
    top: -192%;
    left: -61%;
    width: 16%;
    height: 231%;
    transform: rotate(-39deg);
    background: linear-gradient(150deg, #985f2a, #a08435);
  }
  &__border-bottom {
    position: absolute;
    top: 60%;
    left: 148%;
    width: 16%;
    height: 231%;
    transform: rotate(-41deg);
    background: linear-gradient(150deg, #985f2a, #a08435);
  }
  &__border-left {
    position: absolute;
    top: 31%;
    left: -89%;
    width: 16%;
    height: 231%;
    transform: rotate(-126deg);
    background: linear-gradient(150deg, #985f2a, #a08435);
  }
  &__border-right {
    position: absolute;
    top: -165%;
    left: 173%;
    width: 16%;
    height: 231%;
    transform: rotate(-126deg);
    background: linear-gradient(150deg, #985f2a, #a08435);
  }
}
</style>
