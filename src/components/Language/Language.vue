<script setup>
    import { ref } from 'vue'
    import './style.scss'
    const lang = ref('EN')
    const langIcon = ref('/src/assets/Header-img/icon_en.png')
    
    const languages = ref([
        {id: 1, name: 'EN', icon: 'src/assets/Header-img/icon_en.png'},
        {id: 2, name: 'RU', icon: 'src/assets/Header-img/icon_ru.png'},
        {id: 3, name: 'SW', icon: 'src/assets/Header-img/icon_sw.png'},
    ])
    function selectLang(id) {
        lang.value = languages.value.find(lang => lang.id === id).name
        langIcon.value = languages.value.find(lang => lang.id === id).icon
    }
</script>
    
<template>
    <div class="lang-menu">

        <img class="selected-lang__flag" :src="langIcon">
        <span class="selected-lang__title">{{ lang }}</span>
        <img class="dropdown-arrow" src="./../../assets/Header-img/Arrow.png">

        <ul class="select-lang__lang-list">
            <!-- <div class="lang-list__arrow"></div> -->

            <li v-for="lang in languages" :id="lang.id" class="lang-list__item" @click="selectLang(lang.id)">
                <img class="select-lang__flag-icon" :src="lang.icon">
                <span class="lang-list__title">{{ lang.name }}</span>
            </li>
        </ul>

    </div>
</template>