<template>
  <div class="curtain"></div>
</template>

<script>
export default {
  name: 'Curtain',
}
</script>

<style lang="scss" scoped>
.curtain {
  position: fixed;
  left: -300vw;
  top: 0;
  z-index: 999;
  width: 300vw;
  height: 100vh;
  clip-path: polygon(5% 0, 90% 0, 100% 100%, 0% 100%);
  background: #FFCB46;

  &.move-to-right {
    transition: 3s ease-in-out, clip-path 1s ease-in;
    left: 300vw;
    clip-path: polygon(0% 0, 100% 0, 100% 100%, 0% 100%);
  }
}
</style>
