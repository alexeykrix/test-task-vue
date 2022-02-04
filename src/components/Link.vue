<template>
  <a :href="linkHref" @click="followLink($event)" class="nav-link">
    {{ linkText }}
  </a>
</template>

<script>
export default {
  name: 'Link',
  props: ['linkText', 'linkHref'],
  methods: {
    followLink(e) {
      e.preventDefault()

      const curtain = document.querySelector('.curtain')
      curtain.classList.add('move-to-right')
      setTimeout(() => {
        this.$root.$children[0].page = this.linkHref.slice(1)
      }, 1400)
      setTimeout(() => {
        curtain.classList.remove('move-to-right')
      }, 3000)
    },
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/main.scss';

.nav-link {
  font-family: 'Grtsk Giga', sans-serif;
  font-size: 2.1vh;
  line-height: 140%;
  text-align: center;
  color: $text-color;
  text-decoration: none;
  font-weight: 600;
  transition: color 0.3s ease;
  position: relative;

  @include _1024 {
    font-size: 1.82vmin;
  }
  @include _768 {
    font-size: 1.82vmin;
  }
  @include _440 {
    font-size: 2.1vh;
    position: relative;
  }
}
.nav-link::after {
  position: absolute;
  bottom: -6px;
  left: 0;
  content: '';
  background: #fff;
  width: 0%;
  height: 3px;
  transition: 0.3s ease;
}

.nav-link:hover {
  color: #fff;
}

.nav-link:hover::after {
  width: 100%;
}
</style>