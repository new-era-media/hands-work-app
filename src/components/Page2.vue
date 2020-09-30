<template>
  <div class="size">
    <div class="title">
      <h2>Принципы работы</h2>
    </div>
    <div class="content">
      <div class="content-text">
        <div class="content-container">
          <div class="content-container__number">1</div>
          <div class="content-container__text">
            ВСЕ ЗАЯВКИ ОТ ЮРИДИЧЕСКИХ ЛИЦ, <br />
            ПО-ЭТОМУ НУЖНО <br />
            <span class="color-green"> СТАТЬ САМОЗАНЯТЫМ</span>
          </div>
        </div>
        <div class="content-container">
          <div class="content-container__number">2</div>
          <div class="content-container__text">
            <span class="color-grey"
              >ЕСЛИ ВЗЯЛИ ЗАЯВКУ, ТО НУЖНО ЕЕ ВЫПОЛНИТЬ</span
            >
            Т.Е. ПОЕХАТЬ И ОТРАБОТАТЬ СМЕНУ
          </div>
        </div>
        <div class="content-container">
          <div class="content-container__number">3</div>
          <div class="content-container__text">
            <span class="color-red">ОТКАЗАТЬСЯ</span> ОТ ВЫПОЛНЕНИЯ ЗАЯВКИ
            <span class="color-red"
              >МОЖНО НЕ МЕНЕЕ ЧЕМ ЗА 10 ЧАСОВ ДО НАЧАЛА</span
            >
            РАБОТЫ
          </div>
        </div>
      </div>
    </div>
    <div class="sliders">
      <button @click="nextStep" :class="{ 'button-dark': this.step > 2 }">
        {{ this.step === this.steps ? "Готово" : "Далее" }}
      </button>
      <div class="slide">
        <ul>
          <li
            v-for="(item, i) in steps"
            :key="i"
            :class="{ active: ++i === step }"
          ></li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["step", "steps"],
  methods: {
    nextStep() {
      this.$emit('nextStep')
    },
  },
};
</script>
<style lang="scss" scoped>
.size{
  background: url('../assets/bg2.jpg');
}
.content {
  display: flex;
  align-items: center;
  flex: 1 0 100% !important;
}
.content-container {
  display: flex;
  align-items: center;
  color: white;
  margin: 10px 0 !important;
  &__number {
    width: 84px !important;
    text-align: center;
    margin: 0 15px !important;
    font-size: 114px;
  }
  &__text {
    margin-left: 15px !important;
    font-size: 18px;
    line-height: 23px !important;
    .color-green {
      background-color: #7dbe7a !important;
      border-radius: 10px;
      padding: 2.5px !important;
    }
    .color-grey {
      background-color: #8090a7 !important;
      border-radius: 10px;
      padding: 2.5px !important;
    }
    .color-red {
      background-color: #c12323 !important;
      border-radius: 10px;
      padding: 2.5px !important;
    }
  }
}
.content-container:nth-child(even) {
  flex-direction: row-reverse !important;
  .content-container__text {
    text-align: right !important;
    margin: 0 !important;
  }
}
@media screen and (max-width: 379px) {
  .content {
    margin: 0 5px 0 0 !important;
    padding: 0 !important;
  }
  .content-container {
    &__number {
      font-size: 80px;
    }
    &__text {
      font-size: 14px;
    }
  }
}
</style>