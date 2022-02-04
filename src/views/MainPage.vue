<template>
  <section class="container">
    <Header />
    <Heading 
      headingFirstLine="full-cycle"
      headingSecondLine="event agency" 
    />
    <RunningLine />
    <RunningLine class="line-reverse" />
    <CircularText />
  </section>
</template>

<script>
import Header from '@/components/Header.vue'
import Heading from '@/components/Heading.vue'
import RunningLine from '@/components/RunningLine.vue'
import CircularText from '@/components/CircularText.vue'

export default {
  name: 'Main',
  components: {
    Header,
    Heading,
    RunningLine,
    CircularText
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/main.scss';

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  background: radial-gradient(circle,#FFCB46 25%, transparent 35%);
  @include _1024 {
    background: radial-gradient(circle,#FFCB46 32%, transparent 45%);
  }
}
</style>