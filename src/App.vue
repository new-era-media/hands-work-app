<template>
  <div id="app">
    <DynamicPages :step="step">
      <template #step1>
        <Page1 @nextStep="nextStep" :step="step" :steps="steps" />
      </template>

      <template #step2>
        <Page2 @nextStep="nextStep" :step="step" :steps="steps" />
      </template>

      <template #step3>
        <Page3 @nextStep="nextStep" :step="step" :steps="steps" />
      </template>

      <template #step4>
        <Page4 @nextStep="nextStep" :step="step" :steps="steps" />
      </template>

      <template #step5>
        <Page5 @nextStep="nextStep" :step="step" :steps="steps" />
      </template>
    </DynamicPages>
  </div>
</template>

<script>
import DynamicPages from "@/components/DynamicPages";
import Page1 from "@/components/Page1";
import Page2 from "@/components/Page2";
import Page3 from "@/components/Page3";
import Page4 from "@/components/Page4";
import Page5 from "@/components/Page5";
export default {
  name: "App",
  components: { DynamicPages, Page1, Page2, Page3, Page4, Page5 },
  data() {
    return {
      step: 1,
      steps: 5,
    };
  },
  methods: {
    nextStep() {
      if (this.step < this.steps) {
        this.step++;
      } else {
        this.step = 1;
      }
    },
  },
};
</script>