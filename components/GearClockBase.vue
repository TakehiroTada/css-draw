<template>
  <div class="layout__gear-clock" :style="clockSize">
    <!-- 外側のギザギザ用 -->
    <div class="layout__gear-clock__large-circle">
      <div class="layout__gear-clock__large-circle__bar1" />
      <div class="layout__gear-clock__large-circle__bar2" />
      <div class="layout__gear-clock__large-circle__bar3" />
      <div class="layout__gear-clock__large-circle__bar4" />
      <!-- 中央の扇型用 -->
      <div class="layout__gear-clock__middle-circle">
        <!-- 中央の小さな円用 -->
        <div class="layout__gear-clock__small-circle">
          <div class="layout__gear-clock__small-circle__hand">
            <div class="layout__gear-clock__small-circle__hand__second">
              <div
                class="layout__gear-clock__small-circle__hand__second-hand"
              />
            </div>
            <div class="layout__gear-clock__small-circle__hand__hour">
              <div class="layout__gear-clock__small-circle__hand__hour-hand" />
            </div>
            <div class="layout__gear-clock__small-circle__hand__minute">
              <div
                class="layout__gear-clock__small-circle__hand__minute-hand"
              />
            </div>
            <!-- <div class="layout__gear-clock__small-circle__hand__ellipse" /> -->
          </div>
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
@keyframes right-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
.layout__gear-clock {
  display: flex;
  justify-content: center;
  align-items: center;
}
.layout__gear-clock__large-circle {
  z-index: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 80%;
  height: 80%;
  border-radius: 50%;
  /* 背景色のグラデーション */
  background: linear-gradient(150deg, #985f2a, #a08435);

  position: relative;
  &__bar1 {
    position: absolute;
    width: 8%;
    height: 115%;
    top: -7%;
    background: linear-gradient(150deg, #985f2a, #a08435);
  }
  &__bar2 {
    position: absolute;
    width: 8%;
    height: 115%;
    top: -7%;
    background: linear-gradient(150deg, #985f2a, #a08435);
    transform: rotate(45deg);
  }
  &__bar3 {
    position: absolute;
    width: 8%;
    height: 115%;
    top: -7%;
    background: linear-gradient(150deg, #985f2a, #a08435);
    transform: rotate(90deg);
  }
  &__bar4 {
    position: absolute;
    width: 8%;
    height: 115%;
    top: -7%;
    background: linear-gradient(150deg, #985f2a, #a08435);
    transform: rotate(135deg);
  }
}
.layout__gear-clock__middle-circle {
  z-index: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 88%;
  height: 88%;
  border-radius: 50%;
  background: black;
}
.layout__gear-clock__small-circle {
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 2;
  position: relative;
  width: 18%;
  height: 18%;
  border-radius: 50%;
  background: linear-gradient(150deg, #985f2a, #a08435);

  &__hand {
    display: flex;
    position: relative;
    width: 100%;
    height: 100%;
    display: flex;
    width: 45%;
    height: 45%;
    border-radius: 50%;
    background: white;
    &__second {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0%;
      left: 0%;
      animation-name: right-spin;
      animation-duration: 60s;
      animation-iteration-count: infinite;
      animation-timing-function: linear;
      transform-origin: center;
      &-hand {
        width: 9%;
        height: 579%;
        margin-top: -579%;
        background-color: blue;
      }
    }
    &__hour {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0%;
      left: 0%;
      animation-name: right-spin;
      animation-duration: 30s;
      /* animation-duration: 86400s; */
      animation-iteration-count: infinite;
      animation-timing-function: linear;
      transform-origin: center;
      &-hand {
        width: 9%;
        height: 579%;
        margin-top: -579%;
        background-color: red;
      }
    }
    &__minute {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0%;
      left: 0%;
      animation-name: right-spin;
      /* animation-duration: 3600s; */
      animation-duration: 10s;
      animation-iteration-count: infinite;
      animation-timing-function: linear;
      transform-origin: center;
      &-hand {
        width: 9%;
        height: 579%;
        margin-top: -579%;
        background-color: yellow;
      }
    }

    &__ellipse {
      position: absolute;
      top: 20%;
      left: 19%;
      width: 60%;
      height: 60%;
      border-radius: 50%;
      background: black;
    }
  }

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
