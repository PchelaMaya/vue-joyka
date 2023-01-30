<script setup> 
    import { ref } from 'vue'
    import Language from '@/components/Language/Language.vue'
    
    const isOpenedMobileMenu = ref(false);
    const isActive = ref([
      {
        activeMenu: true
      }
    ])
    function isOpenedMenu() {
      isOpenedMobileMenu.value = !isOpenedMobileMenu.value;
      if (isActive.activeMenu) {
        document.body.style.overflow = 'hidden'
      } else {
        document.body.style.overflow = 'visible'
      }
    }  
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
      <div class="header-mobile-menu">
      <div class="menu-icon-wrapper" @click="isOpenedMenu">
        <div class="menu-icon" 
        :class="{'menu-icon': true, 'menu-icon--active': isOpenedMobileMenu}"
        ></div>
      </div>   
      </div>
    </div>
      <nav
      :class="{'header__navbar-mobile':true, 'header__navbar-mobile--active': isOpenedMobileMenu}">
        <ul>
          <li><a href="#">Как это работает?</a></li>
          <li><a href="#">Кто мы?</a></li>
          <li><a href="#">Поводы для отправки</a></li>
          <li><a href="#">FAQ</a></li>
          <li><a href="#">Отзывы</a></li>
        </ul>
      </nav>
  </header>
</template>
<style lang="scss">
    @import './style.scss';
    @import './mob.scss'
</style>