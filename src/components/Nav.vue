<template>
  <nav class="nav">
    <button class="nav-btn"></button>
    <ul class="nav-list">
     <li class="nav-item item-left">
        <Link class="link" linkText="where?" linkHref="#second" />
      </li>
      <li class="nav-item item-bottom">
        <Link class="link" linkText="who?" linkHref="#second" />
      </li>
      <li class="nav-item item-right">
        <Link class="link" linkText="what?" linkHref="#second" />
      </li>
    </ul>
  </nav>
</template>

<script>
import Link from '@/components/Link.vue'

export default {
  name: 'Nav',
  components: {
    Link
  }
}
</script>

<style scoped lang="scss">
@import '@/assets/main.scss';

.nav {
  flex-grow: 1;
  z-index: 22;
  width: 100%;

  @include _440 {
    width: 100%;
    height: auto;
    margin-bottom: auto;
  }
}

.nav-list {
  list-style: none;
  width: 100vw;
  height: 100vh;
  display: flex;
  align-items: center;

  @include _440 {
    margin-top: 20px;
    width: fit-content;
    margin-left: auto;
    height: auto;
    align-items: flex-end;
    justify-content: center;
    flex-direction: column;
    pointer-events: none;
  }
}

.nav-item {
  @include _440 {
    padding: 5px 0;
    opacity: 0;
    transition: 0.3s;
    transition-delay: 0.2s;
  }

  &.item-left {
    margin-right: auto;
    margin-left: -2.5vh;
    transform: rotate(-90deg);
    @include _440 {
      margin: 0;
      margin-right: 10px;
      transform: none;
    }
  }
  &.item-right {
    margin-left: auto;
    margin-right: -1.25vh;
    transform: rotate(90deg);
    @include _440 {
      transition-delay: 0s;
      margin: 0;
      margin-right: 10px;
      transform: none;
    }
  }
  &.item-bottom {
    align-self: flex-end;
    margin-bottom: 2.5vh;
    @include _440 {
      transition-delay: 0.1s;
      margin: 0;
      margin-right: 10px;
      transform: none;
    }
  }
}

.nav-btn {
  display: none;
  width: 22px;
  height: 22px;
  border: none;
  position: relative;
  margin-left: auto;
  background: transparent;
  top: 21px;
  right: 16px;

  &::after,
  &::before {
    content: '';
    width: 22px;
    height: 1px;
    background: #000;
    position: absolute;
    top: 7px;
    left: 0;
  }

  &::after {
    top: 15px;
  }

  @include _440 {
    display: block;
  }
}

.nav-btn:hover ~ .nav-list,
.nav-list:hover {
  pointer-events: all;
}

.nav-btn:hover ~ .nav-list .item-right,
.nav-list:hover .item-right {
  transition-delay: 0.2s;
}
.nav-btn:hover ~ .nav-list .item-left,
.nav-list:hover .item-left {
  transition-delay: 0s;
}
.nav-btn:hover ~ .nav-list .nav-item,
.nav-list:hover .nav-item {
  opacity: 1;
}

</style>
