<template>
  <svg id="circularTextSvg" viewBox="0 0 100 100">
    <path d="M 0,50 a 50,50 0 1,1 0,1 z"
    id="circle" fill="transparent"/>
    <text><textPath xlink:href="#circle">
      showreal   showreal   showreal
    </textPath></text>
    <circle cx="50" cy="50" r="4" fill="black"/>
  </svg>
</template>

<script>
export default {
  name: 'CircularText',
}
</script>

<style scoped lang="scss">
@import '@/assets/main.scss';

#circularTextSvg {
  position: absolute;
  top: 65vh;
  left: 61vw;
  z-index: 33;
  display: block;
  overflow: visible;
  width: 11vh;
  height: 11vh;
  transform: rotate(-90deg);
  animation: rotateText 5s linear 0s infinite;
  animation-play-state: paused;

  @include _1024 {
    width: 14.5vmin;
    top: 66vh;
    left: 63vw;
  }
}
#circularTextSvg:hover {
  animation-play-state: running;
}
#circularTextSvg text {
  fill: #fff;
  font-size: 12px;
  font-family: 'Grtsk Giga', sans-serif;
}

@keyframes rotateText {
  0% { transform: rotate(-90deg) }
  100% { transform: rotate(-450deg) }
}

</style>