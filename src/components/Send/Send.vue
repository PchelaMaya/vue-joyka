<script setup>
    import { ref } from 'vue'
    import './style.scss'
    import { Swiper, SwiperSlide } from 'swiper/vue'
    import { Navigation, Pagination } from 'swiper'
    import 'swiper/scss'

    const slides = ref([
        {
            img: 'src/assets/Send-img/slider_1.jpg', 
            title: 'Удивить родных', 
            subtitle: 'Встретились со знаменитостью? Веселитесь на концерте любимой группы? Отдыхаете на экзотическом пляже? Такие фото обязательно должны быть в семейном альбоме!'},
        {
            img: 'src/assets/Send-img/slider_2.jpg', 
            title: 'Пригласить друзей на вечеринку', 
            subtitle: 'От приглашения, переданного лично в руки, настрой хорошо повеселиться обеспечен'},
        {
            img: 'src/assets/Send-img/slider_3.jpg', 
            title: 'Прислать привет из путешествия', 
            subtitle: 'В любой точке мира — вы рядом со своими близкими.'},
        {   
            img: 'src/assets/Send-img/slider_4.jpg', 
            title: 'Подарить радость просто так!', 
            subtitle: 'Наша жизнь наполнена рутиной. Отправленная JoyKa с тёплыми словами подарит вашим близким хорошее настроение и улыбку на весь день.'},
        {
            img: 'src/assets/Send-img/slider_5.jpg', 
            title: 'Поделиться воспоминаниями', 
            subtitle: 'Фотография с фразой: «Помнишь, как классно было?» вызовет волну положительных эмоций и желание встретиться снова.'}
    ])
    const navigation = {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev'
    }
     const pagination = {
        el: '.swiper-pagination',
        type: 'fraction',
            // type: 'custom',
            // renderCustom: (index, current, total) => {
            //     if (current < 10) current = '0' + current
            //     if (total < 10) total = '0' + total
            //     const curElem = '<span style="font-weight: 700; font-size: 24px; color: #2783FE;">'+current+'</span>'
            //     const totalElem = '<span class="swiper-pagination-current">'+total+'</span>'
            //     return curElem + ' / ' + totalElem
            // }
    }
    const breakpoints = {

        slidesPerView: 3,
    }

</script>
<template>
    <section class="send">
        <div class="send__container w-send">
            <div class="send__content">
            <h2 class="send__title">Поводы для отправки</h2>
                <swiper 
                :space-between="30" 
                :breakpoints="breakpoints"
                :modules="[Navigation, Pagination]" 
                :navigation="navigation" 
                :pagination="pagination">
                <SwiperSlide
                v-for="slide in slides">
                <div class="swiper-slide">
                    <img class="slider__item" 
                    :src="slide.img">
                    <div class="sliders__text">
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
                    <p class="slider__text">Листайте дальше</p>
                    <div class="swiper-pagination"></div>
                    </div>
                
                </swiper>

            
            </div>
        </div>

    </section>
</template>