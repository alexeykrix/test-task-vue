<template>
  <h1 class="heading" ref="heading">
    {{ headingFirstLine }} <br>
    {{ headingSecondLine }}
  </h1> 
</template>

<script>
export default {
  name: 'Heading',
  props: ['headingFirstLine', 'headingSecondLine'],
  data() {return {
    screenWidth: window.innerWidth,
    screenHeight: window.innerHeight
  }},
  methods: {
    handleMousemove(e) {
      const 
      mouseX = e.clientX,
      mouseY = e.clientY,
      moveX = (this.screenWidth/2 - (this.screenWidth - mouseX)) * 0.02,
      moveY = (this.screenHeight/2 - (this.screenHeight - mouseY)) * 0.02
      
      if (!this.$refs.heading) return
      this.$refs.heading.style.transform = `
        translate(${moveX}px, ${moveY}px)
      `
    },
    touchHandler() {
      this.$refs.heading.style.transition = '0.8s ease'
    },
  },
  mounted() {
    document.addEventListener('mousemove', this.handleMousemove)
    document.addEventListener('touchstart', this.touchHandler)
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/main.scss';

.heading {
  position: fixed;
  font-family: 'Grtsk Giga', sans-serif;
  font-weight: bold;
  font-size: 10vh;
  line-height: 110%;
  text-align: center;
  text-transform: uppercase;
  color: $text-color;

  @include _1024 {
    font-size: 7.55vh;
  }
  @include _768 {
    font-size: 7.55vmin;
    padding: 0 3vmin;
  }
  @include _440 {
    font-size: 34px;
  }
}
</style>
