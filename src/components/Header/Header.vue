<script setup>
    
    import { ref } from 'vue'
    import Language from './../Language/Language.vue'
    // import './'
</script>
<template>
    <!-- <header class="header">
        <div class="header__inner w-inner">
                <div class="nav__logo">
                    <a href="/"><img src="@/assets/Header-img/Logo.png" alt="Image"></a>
                </div>
                <ul class="nav__list nav__list--header">
                    <li><a href="#!">Как это работает?</a></li>
                    <li><a href="#!">Кто мы?</a></li>
                    <li><a href="#!">Поводы для отправки</a></li>
                    <li><a href="#!">FAQ</a></li>
                    <li><a href="#!">Отзывы</a></li>
                </ul>
                <div class="lang-menu">
                    <div class="dropdown-lang">
                        <a href="#!" class="selected-lang">EN</a>
                        <ul class="lang__list">
                            <li class="en"><a href="#!">EN</a></li>
                            <li class="ru"><a href="#!">RU</a></li>
                            <li class="sw"><a href="#!">SW</a></li>
                        </ul>
                        <div class="dropdown-arrow">
                            <img src="@/assets/Header-img/Arrow.png" width="22" height="12.5">
                        </div>
                    </div>
                </div>
        </div>

</header> -->
<header class="header">
    <div class="header__inner w-inner">

      <div class="header__logo">
        <a href="/">
          <img src="@/assets/Header-img/logo.png">
        </a>
      </div>

     
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