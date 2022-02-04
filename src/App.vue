<template>
  <div id="app" @nextScreen="nextScreen()">
    <MainPage v-if="page === 'main'" />
    <SecondPage v-if="page === 'second'" />
    <Curtain />
  </div>
</template>

<script>
import MainPage from '@/views/MainPage.vue'
import SecondPage from '@/views/SecondPage.vue'
import Curtain from '@/components/Curtain.vue'

export default {
  name: 'App',
  components: { 
    MainPage,
    SecondPage,
    Curtain
  },
  data() {return {
    page: 'main'
  }},
  methods: {
    nextScreen() {
      
      this.page = 'second'
    }
  }

}
</script>

<style lang="scss">
@import '@/assets/main.scss';




</style>
