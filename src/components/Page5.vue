<template>
  <div class="size">
    <div class="title">
      <h2 style="color: #405378 !important">Вся информация внутри заказа</h2>
    </div>
    <div class="content">
      <div class="img"></div>
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
      this.$emit("nextStep");
    },
  },
};
</script>
<style lang="scss" scoped>
.size {
  background: url("../assets/bg4.jpg");
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.img {
  width: 98vw;
  height: 98vw;
  background: url("../assets/5.png") no-repeat center center;
  background-size: 100%;
}
h2 .content {
  display: flex;
  align-items: center;
  flex: 1 0 100% !important;
}
</style>