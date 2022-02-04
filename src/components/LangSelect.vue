<template>
  <div class="lang-select">
    <button class="lang-btn">👅</button>
    <ul class="lang-list">
      <li class="lang-list__item">RU</li>
      <li class="lang-list__item">UA</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'LangSelect',
}
</script>

<style scoped lang="scss">
@import '@/assets/main.scss';

.lang-select {
  position: absolute;
  left: 20px;
  top: 20px;
  z-index: 33;

  @include _440 {
    top: 16px;
    left: 16px;
  }
}
.lang-btn {
  background: transparent;
  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 50%;
  font-family: 'Body Grotesque';
  font-size: 1.74vh;
  width: 4.4vh;
  height: 4.4vh;
  cursor: pointer;
  
  @include _440 {
    width: 34px;
    height: 34px;
  }
}
.lang-list {
  overflow: hidden;
  position: absolute;
  padding-left: 6vh;
  left: 0;
  top: 0;
  list-style: none;
  display: flex;
  transition: 0.3s;
  transition-delay: 1s;
  pointer-events: none
}
.lang-list__item {
  opacity: 0;
  font-family: 'Grtsk Giga', sans-serif;
  font-weight: 700;
  color: $text-color;
  margin-right: 10px;
  cursor: pointer;
  transition: opacity 0.5s;
  line-height: 4.4vh;

  &:nth-child(1) {
    transition-delay: 0.3s;
  }
  &:hover {
    color: #fff;
  }
}

.lang-btn:hover ~ .lang-list,
.lang-list:hover {
  pointer-events: all;
}
.lang-btn:hover ~ .lang-list .lang-list__item,
.lang-list:hover .lang-list__item {
  opacity: 1;
  transition-delay: 0s;
}
.lang-btn:hover ~ .lang-list .lang-list__item:nth-child(2),
.lang-list:hover .lang-list__item:nth-child(2) {
  transition-delay: 0.3s;
}
</style>
