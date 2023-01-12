<script setup>
    import { ref } from 'vue'
</script>
<template>
    <section class="main">
        <div class="container__main w-main">
            <div class="main__about">
                <h1 class="main__title">JoyKa — эмоции в конверте 
                    Дари моменты радости 
                    вместе с JoyMail!</h1>
                <ul class="main__list">
                    <li class="delivery">Доставка из любой точки мира</li>
                    <li class="time">За 12 часов</li>
                    <li class="hand">Лично в руки адресату</li>
                </ul>
                <div class="main__media">
                    <a href="#!" class="btn">Отправить Джойку
                        <img class="main__btn--img" src="./../../assets/Main-img/icon_mail.svg" alt="image">
                    </a>
                    <div class="main__video">
                        <img src="./../../assets/Main-img/main-play.svg" alt="Image">
                        <div class="main__video__text">
                            <h2>Посмотрите видеообзор нашего подарка</h2>
                            <p>Время просмотра 1:23 сек</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<style lang="scss">
    @import './style.scss'
</style>