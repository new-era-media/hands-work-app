<template>
  <div class="size">
    <div class="title">
      <h2 style="color: #405378 !important">Подработка для всех</h2>
      <h3 style="color: #565656 !important">заказы для мужчин и женщин</h3>
    </div>
    <div class="content">
      <div class="img1"></div>
      <div class="img2"></div>
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
  background: url('../assets/bg3.jpg');
}
.content {
  flex: 1 0 100% !important;
  display: flex;
  align-items: center;
  justify-content: center;
}
.img1,
.img2 {
  width: 50%;
  height: 300px;
  background-size: 65% !important;
  display: flex;
  align-items: center;
  justify-content: center;
  background-position: 80% 70% !important;
}
.img1 {
  background: url("../assets/female.png") no-repeat;
}
.img2 {
  background: url("../assets/male.png") no-repeat;
}

@media screen and (max-width: 379px) {
  .content {
    margin: 0 !important;
    padding: 0 !important;
  }
}
</style>