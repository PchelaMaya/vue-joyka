<script setup>
    import { reactive } from 'vue'
    import './style.scss'
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
            name: 'Тайланд',
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
        question: 'Выберите город отправления',
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
            name: 'Бангкок',
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
        question: 'Выберите тип JoyKa',
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
        question: 'Выберите страну прибытия',
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
            name: 'Тайланд',
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
  const deltaPercent = 100 / blocks.datas.length
  const deltaPercentMobil = 180 / blocks.datas.length
  const handlerNextButton = () => {
    if (blocks.step !== blocks.datas.length-1) {
      blocks.step++
    }
  }
  const handlerPrevButton = () => {
    if (blocks.step !== 0) {
      blocks.step--
    }
  }
  const handlerSelectAnswer = (e) => {
    blocks.datas[blocks.step].answer = e.target.value
    for (let item in blocks.datas[blocks.step].data) {
      blocks.datas[blocks.step].data[item].selected = false
    }
    blocks.datas[blocks.step].data[e.target.value].selected = true
  }

</script>
<template>
    <section class="travel">
        <div class="travel__content">
          <div class="travel__content_options">
            <p class="travel__content_options-steps">Шаг {{ blocks.step + 1 }} из {{ blocks.datas.length }}</p>
            <div class="travel__content_options_progressBar">
              <div 
                class="travel__content_options_progressBar-moving" 
                :style="{width: deltaPercent * (blocks.step + 1)  + '%'}"></div>
            </div>
            <div>
              <p class="travel__content_options_title-desktop">{{ blocks.datas[blocks.step].title }}</p>
              <div class="DF JCSB FWW travel__content_options-margin-fix">
                <label 
                  v-for="item in blocks.datas[blocks.step].data" 
                  :for='item.id' 
                  class="travel__content_options_item_preview travel__content_options_item_preview-margin_fix">
                  <img 
                    class="travel__content_options_item_preview-img" 
                    :src='item.img' alt="country">
                  <input 
                    class="travel__content_options_item-check" 
                    @click="handlerSelectAnswer" 
                    :id='item.id' name="city" :value='item.value' type="radio" 
                    :checked='item.selected'> 
                  <p class="travel__content_options_item-name">{{item.name}}</p>
                </label>
              </div>
              <div class="travel-buttons">
                <button class="button button-prev" @click="handlerPrevButton">Предыдущий шаг</button>
                <button class="button button-next" @click="handlerNextButton">Следующий шаг</button>
              </div>
            </div>
          </div>
        </div>
      </section>
    <!-- <section class="travel">
        <div class="travel__container">
             -->
            <!-- <div class="travel__progress">
                <label for="file">Шаг 1 из 5</label>
                <progress id="file" max="5" value="1">1</progress>
            </div>
            <div class="travel__content"></div>
            <div class="buttons">
            <a href="#!" class="button button-prev">Предыдущий шаг</a>
            <a href="#!" class="button button-next">Следующий шаг</a>
            </div> -->
<!--             
        </div>

    </section> -->
    <!-- <section class="travel">
        <div class="travel_content DF AIC">
          <div class="travel_content_options">
            <p class="travel_content_options-steps">Шаг {{ data.quizeQuestion.step + 1 }} из {{ data.quizeQuestion.step.length }}</p>
            <div class="travel_content_options_progressBar">
              <div 
                class="travel_content_options_progressBar-moving" 
                :style="{width: deltaPercent * (data.quizeQuestion.step + 1)  + '%'}"></div>
            </div>
            <div>
              <div class="travel_content_options_steps container">
                <p class="travel_content_options_title">{{ data.quizQuestions[data.quizeQuestion.step].title }}</p>
              </div>
              <p class="travel_content_options_title-desktop">{{ data.quizQuestions[data.quizeQuestion.step].title }}</p>
              <div class="DF JCSB FWW quiz_body_options-margin-fix">
                <label 
                  v-for="item in data.quizQuestions[data.quizeQuestion.step].data" 
                  :for='item.id' 
                  class="travel_content_options_item_preview travel_content_options_item_preview-margin_fix">
                  <img 
                    class="travel_content_options_item_preview-img" 
                    src="/Rectangle 1757.png" alt="country">
                  <input 
                    class="travel_content_options_item-check" 
                    @click="handlerSelectAnswer" 
                    :id='item.id' name="city" :value='item.value' type="radio" 
                    :checked='item.checked'> 
                  <p class="travel_content_options_item-name">{{item.name}}</p>
                </label>
              </div>
              <div class="DF JCSB travel_margin_button_fix">
                <button class="travel_content_options-prev-step DF JCC" @click="handlerPrevButton">Предыдущий шаг</button>
                <button class="travel_content_options-next-step DF JCC" @click="handlerNextButton">Следующий шаг</button>
              </div>
            </div>
          </div>
        </div>
      </section> -->
</template>