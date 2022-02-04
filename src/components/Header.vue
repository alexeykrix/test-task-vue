<template>
  <header class="header">
    <Logo />
    <LangSelect />
    <Nav />
  </header>
</template>

<script>
import LangSelect from './LangSelect.vue'
import Logo from './Logo.vue'
import Nav from './Nav.vue'

export default {
  name: 'Header',
  components: {
    Logo,
    LangSelect,
    Nav
  }
}
</script>

<style scoped lang="scss">
.header {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  display: flex;
  justify-content: center;
}
</style>
