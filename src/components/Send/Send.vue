<script setup>
    import { ref } from 'vue'
    import './style.scss'
    import './mob.scss'
    import { Swiper, SwiperSlide } from 'swiper/vue'
    import { Navigation, Pagination } from 'swiper'
    import 'swiper/scss'

    const slides = ref([
        {
            img: 'src/assets/Send-img/slider_8.jpg', 
            title: 'Удивить родных и близких', 
            subtitle: 'Встретились со знаменитостью? Веселитесь на концерте любимой группы? Отдыхаете на экзотическом пляже? Такие фото обязательно должны быть в семейном альбоме!'},

        {
            img: 'src/assets/Send-img/slider_1.jpg', 
            title: 'Пригласить друзей на вечеринку', 
            subtitle: 'От приглашения, переданного лично в руки, настрой хорошо повеселиться обеспечен'},

        {
            img: 'src/assets/Send-img/slider_2.jpg', 
            title: 'Прислать привет из путешествия', 
            subtitle: 'В любой точке мира — вы рядом со своими близкими.'},
           
        {
            img: 'src/assets/Send-img/slider_3.jpg', 
            title: 'Подарить радость просто так!', 
            subtitle: 'Наша жизнь наполнена рутиной. Отправленная JoyKa с тёплыми словами подарит вашим близким хорошее настроение и улыбку на весь день.'},

        {   
            img: 'src/assets/Send-img/slider_4.jpg', 
            title: 'Поделиться воспоминаниями', 
            subtitle: 'Фотография с фразой: «Помнишь, как классно было?» вызовет волну положительных эмоций и желание встретиться снова.'},   
   

        {      
            img: 'src/assets/Send-img/slider_5.jpg', 
            title: 'Передать привет родителям', 
            subtitle: 'Ваше счастливое фото порадует их больше любого звонка и напомнит им о ваших чувствах.'},
        {
            img: 'src/assets/Send-img/slider_6.jpg', 
            title: 'Поздравить с праздником', 
            subtitle: 'Удивить друзей, порадовать родных — какая идея может быть лучше для праздника, чем JoyKa?'},
        {   
            img: 'src/assets/Send-img/slider_7.jpg', 
            title: 'Вдохновить близких своими победами', 
            subtitle: 'Забил решающий гол? Покорил очередкую вершину? Отправь JoyKa — пусть друзья разделят с тобой радость момента.'}

    ])
    const navigation = {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev'
    }
    const pagination = {
        el: '.swiper-pagination',
        type: 'fraction',

    }
    const breakpoints = {
        0: {
            slidesPerView: 0,
            navigation: 'false'
        },
        630: {
            slidesPerView: 2,
        },
        1300: {
            slidesPerView: 3
        },
        3000: {
            slidesPerView: 4
        },
    }
</script>
<template>
    <section class="send">
        <div class="w-inner w-inner--send">
            <div class="send__content">
            <h2 class="send__title">Поводы для отправки</h2>
                <swiper 
                :space-between="30" 
                :slidesPerView="3"
                :breakpoints="breakpoints"
                :modules="[Navigation, Pagination]" 
                :navigation="navigation" 
                :pagination="pagination">
                <SwiperSlide
                v-for="slide in slides">
                <div class="swiper-slides">
                    <div class="slider__item" :style="{ backgroundImage: `url(${slide.img})` }">
                    </div>
                    <div class="slider__text">
                        <h2 class="slider__title">{{ slide.title }}</h2>
                        <p class="slider__subtitle">{{ slide.subtitle }}</p>
                    </div>
                </div>
                </SwiperSlide>
                <div class="buttons">
                    <button class="slider__btn swiper-button-prev">
                        <img src="@/assets/Send-img/arrow-left.svg" alt="">
                    </button>
                    <button class="slider__btn swiper-button-next">
                        <img src="@/assets/Send-img/arrow-right.svg" alt="">
                    </button>
                    <p class="pagination__text">Листайте дальше</p>
                    <div class="swiper-pagination"></div>
                </div>
                </swiper>
            </div>
        </div>
    </section>
</template>