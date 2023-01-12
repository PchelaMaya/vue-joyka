<script setup>
    
    import { ref } from 'vue'
    import Language from './../Language/Language.vue'
    // import './'
</script>
<template>
<header class="header">
    <div class="header__inner w-inner">
        <a class="header__logo" href="/">
          <img src="@/assets/Header-img/logo.png">
        </a>
      <nav class="header__navbar">
        <ul>
          <li><a href="#">Как это работает?</a></li>
          <li><a href="#">Кто мы?</a></li>
          <li><a href="#">Поводы для отправки</a></li>
          <li><a href="#">FAQ</a></li>
          <li><a href="#">Отзывы</a></li>
        </ul>
      </nav>
      <Language />
    </div>
  </header>
</template>
<style lang="scss">
    @import './style.scss'
</style>