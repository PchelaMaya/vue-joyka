<script setup>
    import { ref } from 'vue'
    import './style.scss'
</script>
<template>
    <section class="working">
        <h2 class="working__title">Как это работает?</h2>
        <div class="container__working w-inner">

            <div class="point_works--item point_works--selfi">
                <div class="selfi__img">
                    <img src="@/assets/Working-img/selphi.png" alt="Image">
                </div>
                <div class="works__text works__text--selfi">
                    <h2 class="works__text--title">Человек делает селфи</h2>
                    <p class="works__text--text">Вы делаете селфи
                        или выбираете удачное фото
                        из галереи JoyKa</p>
                </div>
            </div>
            <div class="point_works--item point_works--injoy">
                <div class="injoy__img">
                    <img src="@/assets/Working-img/injoy.png" alt="Image">
                </div>
                <div class="works__text works__text--injoy">
                    <h2 class="works__text--title">Конверт JoyKa
                        с ярким фото</h2>
                    <p class="works__text--text">Оставляете заявку на сайте
                        или в приложении. Две минуты —
                        и JoyKa готова!</p>
                </div>
            </div>
            <div class="point_works--item point_works--courier">
                <div class="courier__img">
                    <img src="@/assets/Working-img/courier.png" alt="Image">
                </div>
                <div class="works__text works__text--courier">
                    <h2 class="works__text--title">Курьер
                        несёт JoyKa</h2>
                    <p class="works__text--text">Распечатанную фотографию
                        в красивом конверте курьер 
                        доставит лично в руки адресату</p>
                </div>
            </div>

        </div>
            <div class="receiving w-inner">
                <div class="receiving__background"></div>
                <div class="receiving__content">
                    <h2 class="receiving__content--title">Адресат радуется полученной JoyKa</h2>
                    <p class="receiving__content--text">Ваше фото с личным посланием подарят 
                        близким хорошее настроение на весь день</p>
                    <div class="receiving--btn">
                    <a href="#!" class="btn">Отправить Джойку
                        <img class="btn--img" src="@/assets/Main-img/icon_mail.svg" alt="image">
                    </a>
                    </div>
                </div>
            
        </div>

    </section>
</template>