<script setup>
    import { reactive } from 'vue'
    import './style.scss'
    import './mob.scss'
    const blocks = reactive({
    step: 0,
    datas: [
      {
        title: 'Выберите страну отправления',
        answer: null,
        data: [
          {
            name: 'Украина',
            id: 'country-1',
            value: 0,
            selected: true,
            img: '/src/assets/Travel-img/travel-ukrine.png',
          },
          {
            name: 'Грузия',
            id: 'country-2',
            value: 1,
            selected: false,
            
            img: '/src/assets/Travel-img/travel-gruziya.png',
          },
          {
            name: 'Россия',
            id: 'country-3',
            value: 2,
            selected: false,
            img: '/src/assets/Travel-img/travel-tailand.png',
          },
          {
            name: 'Ещё страна',
            id: 'country-4',
            value: 3,
            selected: false,
            img: '/src/assets/Travel-img/travel-other.png',
          }
        ]
      },
      {
        title: 'Выберите город отправления',
        answer: null,
        data: [
          {
            name: 'Киев',
            id: 'city-1',
            value: 0,
            selected: true,
            img: '/src/assets/Travel-img/travel-ukrine.png',
          },
          {
            name: 'Тбилиси',
            id: 'city-2',
            value: 1,
            selected: false,
            
            img: '/src/assets/Travel-img/travel-gruziya.png',
          },
          {
            name: 'Москва',
            id: 'city-3',
            value: 2,
            selected: false,
            img: '/src/assets/Travel-img/travel-tailand.png',
          },
          {
            name: 'Ещё страна',
            id: 'city-4',
            value: 3,
            selected: false,
            
            img: '/src/assets/Travel-img/travel-other.png',
          }
        ]
      },
      {
        title: 'Выберите тип JoyKa',
        answer: null,
        data: [
          {
            name: 'White JoyKa',
            id: 'white',
            value: 0,
            selected: true,
            img: '/src/assets/Travel-img/travel-white.png',
          },
          {
            name: 'Craft JoyKa',
            id: 'craft',
            value: 1,
            selected: false,
            
            img: '/src/assets/Travel-img/travel-craft.png',
          },
          {
            name: 'Манускрипт',
            id: 'manuscript',
            value: 2,
            selected: false,
            img: '/src/assets/Travel-img/travel-manuscript.png',
          },
          {
            name: 'Другой тип',
            id: 'other',
            value: 3,
            selected: false,
            
            img: '/src/assets/Travel-img/travel-other.png',
          }
        ]
      },
      {
        title: 'Выберите страну получателя',
        answer: null,
        data: [
          {
            name: 'Украина',
            id: 'country--1',
            value: 0,
            selected: true,
            img: '/src/assets/Travel-img/travel-ukrine.png',
          },
          {
            name: 'Грузия',
            id: 'country--2',
            value: 1,
            selected: false,
            
            img: '/src/assets/Travel-img/travel-gruziya.png',
          },
          {
            name: 'Россия',
            id: 'country--3',
            value: 2,
            selected: false,
            img: '/src/assets/Travel-img/travel-tailand.png',
          },
          {
            name: 'Ещё страна',
            id: 'country--4',
            value: 3,
            selected: false,
            
            img: '/src/assets/Travel-img/travel-other.png',
          }
        ]
      },
    ]
  })
  //Заполнение progressBar
  // const r = 40;
  // const circumference = 2 * Math.PI * r;
  const deltaPercent = 100 / blocks.datas.length;
  const deltaProgress = 252 / blocks.datas.length;
  
  const NextButton = () => {
    if (blocks.step !== blocks.datas.length-1) {
      blocks.step++
    }
  }
  const PrevButton = () => {
    if (blocks.step !== 0) {
      blocks.step--
    }
  }
//Выбор ответа
  const SelectAnswer = (e) => {
    blocks.datas[blocks.step].answer = e.target.value
    for (let item in blocks.datas[blocks.step].data) {
      blocks.datas[blocks.step].data[item].selected = false
    }
    blocks.datas[blocks.step].data[e.target.value].selected = true
  }
  // <circle r="40" cx="65" cy="0" fill="none" stroke-width="12" stroke="#2783FE" stroke-dasharray="45 201.2" stroke-dashoffset="1" style="transform: rotate(45deg);"></circle>
</script>
<template>
    <section class="travel">
        <div class="travel__content">
          <div class="travel__content__area">
            <p class="area__steps">Шаг {{ blocks.step + 1 }} из {{ blocks.datas.length }}</p>
            <div class="area__progress">
              <div 
                class="area__progress-moving" 
                :style="{width: deltaPercent * (blocks.step + 1)  + '%'}">
              </div>
            </div>
            <div class="area__progress-mobile" >
              <svg viewbox="0 0 45 45" width="45" height="45">
                <circle r="40" cx="46" cy="46" fill="none" stroke-width="12" stroke="#DAEDFF"/>
                <circle r="40" cx="46" cy="46" fill="none" stroke-width="12" stroke="#2783FE"
                    :stroke-dasharray="deltaProgress * (blocks.step + 1) + ' 252'"
                    stroke-dashoffset="0"
                    transform="rotate(-90 46 46)"></circle>/>    
                <text x="46" y="53" font-family="Ubuntu" font-size="16"
                    text-anchor="middle" fill="#8B96A4">
                    {{ blocks.step + 1 }} из {{ blocks.datas.length }}
                </text>
              </svg>
              <p class="area__title-mobile">{{ blocks.datas[blocks.step].title }}</p>

            </div>
            <div class="area__content">
              <p class="area__title">{{ blocks.datas[blocks.step].title }}</p>
              <div class="area__test">
                <label 
                  v-for="item in blocks.datas[blocks.step].data" 
                  :for='item.id' 
                  class="test__item-preview test__item-preview-test">
                  <img 
                    class="test__item-preview-img" 
                    :src='item.img' alt="country">
                  <input 
                    class="test__item-check" 
                    @click="SelectAnswer" 
                    :id='item.id' name="city" :value='item.value' type="radio" 
                    :checked='item.selected'> 
                  <p class="test__item-name">{{item.name}}</p>
                </label>
              </div>
              <div class="travel-buttons">
                <button class="button button-prev" @click="PrevButton">Предыдущий шаг</button>
                <button class="button button-next" @click="NextButton">Следующий шаг</button>
              </div>
              <div class="buttons-mobile">
                <button class="button button-next" @click="NextButton">Следующий шаг</button>
                <button class="button button-prev" @click="PrevButton">Предыдущий шаг</button>
              </div>
            </div>
          </div>
        </div>
      </section>

</template>