<template>
  <div class="running-line__wrapper" ref="runningLine">
    <div class="running-line__inner">
      <div class="line-half line-half__first">
        <span class="text">FULL-CYCLE EVENT AGENCY</span>
        <span class="text">FULL-CYCLE EVENT AGENCY</span>
      </div>
      <div class="line-half line-half__second">
        <span class="text">FULL-CYCLE EVENT AGENCY</span>
        <span class="text">FULL-CYCLE EVENT AGENCY</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RunningLine',
  data() {return {
    screenWidth: window.innerWidth,
    screenHeight: window.innerHeight
  }},
  mounted() {
    let angle = (Math.atan(this.screenHeight/this.screenWidth) * 180/Math.PI).toFixed(2)
    this.$refs.runningLine.style.transform = `rotate(${-angle}deg)`
    if (this.$refs.runningLine.classList.contains('line-reverse')) {
      this.$refs.runningLine.style.transform = `rotate(${-angle}deg) scale(-1)`
    } 
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/main.scss';

.running-line__wrapper {
  transform: rotate(-30deg);
  position: fixed;
  z-index: -1;
  top: 60%;
  width: 160vw;
  
  @include _1024 {
    top: 51%;
  }
  @include _440 {
    width: 220vw;
  }

  &.line-reverse {
    transform: rotate(-30deg) scale(-1);
    top: 55%;

    @include _1024 {
      top: 50%;
    }
  }
}

.running-line__inner {
  background: #212121;
  position: relative;
  width: 100%;
}

.line-half {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  overflow: hidden;
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  position: absolute;
  top: 0;
  right: 0;
  animation: ticker 30s infinite linear forwards;
  
  &.line-half__second {
    animation: 30s ticker 15s infinite linear forwards;
    text-indent:200%
  }

  .text {
    font-family: 'Grtsk Giga', sans-serif;
    font-style: italic;
    font-weight: bold;
    font-size: 8.62vh;
    line-height: 110%;
    text-transform: uppercase;
    white-space: nowrap;
    opacity: 0.1;
    color: #BEBEBE;
    text-shadow: -1px 0 $text-color, 0 1px $text-color, 1px 0 $text-color, 0 -1px $text-color;

    @include _1024 {
      font-size: 5.46vh;
    }
    @include _768 {
      font-size: 4.1vh;
    }
  }
}


@keyframes ticker {
  0% { text-indent: 100% }
  100% { text-indent: -100% }
}

</style>
