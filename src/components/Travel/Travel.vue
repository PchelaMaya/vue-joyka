<script setup>

    import { ref } from 'vue'
    import './style.scss'
    const data = ref([
    {
        title: 'Выберите страну отправления',
        data: [
        {
            name: 'Украина',
            img: '/src/assets/Travel-img/travel-ukraine.png'
        },
        {
            name: 'Грузия',
            img: '/src/assets/Travel-img/travel-gruziya.png'
        },
        {
            name: 'Тайланд',
            img: '/src/assets/Travel-img/travel-tailand.png'
        },
        {
            name: 'Ещё страна',
            img: '#DAEDFF'
        }
        ]
    },
        
    ])
</script>
<template>
    <section class="travel">
        <div class="travel__container">
            <div class="travel__progress">
                <label for="file">Шаг 1 из 5</label>
                <progress id="file" max="5" value="1">1</progress>
            </div>
            <div class="travel__content"></div>
            <div class="buttons">
            <a href="#!" class="button button-prev">Предыдущий шаг</a>
            <a href="#!" class="button button-next">Следующий шаг</a>
            </div>
        </div>

    </section>
</template>