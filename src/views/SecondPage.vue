<template>
  <section class="other-page">
    <Heading style="font-size: 34px"
      headingFirstLine="Cool page not found"
      headingSecondLine="but never stop trying"
    />
    <Link class="link" linkText="to main page" linkHref="#main" />
  </section>
</template>

<script>
import Heading from '@/components/Heading.vue'
import Link from '@/components/Link.vue'

export default {
  name: 'SecondPage',
  components: {
    Heading,
    Link
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/main.scss';

.other-page {
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

.link {
  position: absolute;
  bottom: 2vh;
}
</style>