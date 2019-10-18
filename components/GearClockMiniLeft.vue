<template>
  <div class="layout__gear-clock-mini" :style="clockSize">
    <!-- 外側のギザギザ用 -->
    <div class="layout__gear-clock-mini__large-circle">
      <div class="layout__gear-clock-mini__large-circle__bar1" />
      <div class="layout__gear-clock-mini__large-circle__bar2" />
      <div class="layout__gear-clock-mini__large-circle__bar3" />
      <div class="layout__gear-clock-mini__large-circle__bar4" />
      <!-- 中央の扇型用 -->
      <div class="layout__gear-clock-mini__middle-circle">
        <!-- 中央の小さな円用 -->
        <div class="layout__gear-clock-mini__small-circle">
          <div class="layout__gear-clock-mini__small-circle__border-top" />
          <div class="layout__gear-clock-mini__small-circle__border-bottom" />
          <div class="layout__gear-clock-mini__small-circle__border-left" />
          <div class="layout__gear-clock-mini__small-circle__border-right" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    size: { type: Number, required: true },
    xPoint: { type: Number, required: true },
    yPoint: { type: Number, required: true },
    backSpin: { type: Boolean, default: false }
  },
  computed: {
    clockSize() {
      return {
        width: this.size + '%',
        height: this.size + '%',
        top: this.xPoint + '%',
        left: this.yPoint + '%'
      }
    }
    // Todo: キーフレームのスタイルが違う名前空間にあるので、実装を検討する必要がある
    // spin() {
    //   return this.backSpin
    //     ? {
    //         'animation-name': 'right-spin',
    //         'animation-duration': '4s',
    //         'animation-iteration-count': 'infinite',
    //         'nimation-timing-function': 'linear'
    //       }
    //     : {
    //         'animation-name': 'left-spin',
    //         'animation-duration': '4s',
    //         'animation-iteration-count': 'infinite',
    //         'nimation-timing-function': 'linear'
    //       }
    // }
  }
}
</script>

<style lang="scss" scoped>
@keyframes left-spin {
  from {
    transform: rotate(360deg);
  }
  to {
    transform: rotate(0deg);
  }
}
.layout__gear-clock-mini {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  animation-name: left-spin;
  animation-duration: 8s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}
.layout__gear-clock-mini__large-circle {
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
.layout__gear-clock-mini__middle-circle {
  z-index: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 88%;
  height: 88%;
  border-radius: 50%;
  background: black;
}
.layout__gear-clock-mini__small-circle {
  z-index: 2;
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
