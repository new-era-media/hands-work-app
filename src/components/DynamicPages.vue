<template>
  <div class="dynamic">
    <slot :name="componentActive"></slot>
  </div>
</template>
<script>
export default {
  props: ["step"],
  computed: {
    componentActive() {
      return `step${this.step}`;
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Comfortaa:wght@300&display=swap");
* {
  margin: 0 !important;
  padding: 0 !important;
  box-sizing: border-box !important;
  font-family: "Comfortaa", cursive !important;
}
.dynamic {
  position: relative;
  height: 100% !important;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: black;
}
.content {
  height: 100% !important;
}
.size {
  width: 100vw;
  max-width: 680px;
  margin: 0 auto !important;
  padding: 0 auto !important;
  display: flex;
  flex-direction: column;
  flex: 1 0 80%;
  background-repeat: no-repeat !important;
  background-size: cover !important;
}
.title {
  justify-content: center;
  color: white;

  h2,
  h3 {
    text-align: center;
  }

  h2 {
    font-weight: 700;
    font-size: 30px;
    margin-top: 40px !important;
    text-transform: uppercase;
  }
  h3 {
    margin-top: 10px !important;
    font-size: 18px;
  }
}
.title,
.sliders {
  padding: 1rem;
  display: flex;
  align-items: center;
  flex-direction: column;
}
.sliders {
  width: 100%;
  height: 100px;
  justify-content: space-between;
  padding: 10px !important;
  .button-dark {
    border: #405378 3px solid !important;
    border-radius: 10px;
    color: #405378 !important;
  }
  button {
    text-transform: uppercase;
    background: transparent;
    border: white 3px solid;
    border-radius: 10px;
    color: white;
    font-size: 21px;
    width: 126px;
    height: 47px;
    &:focus {
      outline: none !important;
    }
  }
  ul {
    width: 150px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    li {
      list-style: none;
      width: 18px;
      height: 18px;
      background: #405378;
      border: 1px solid #364767;
      box-sizing: border-box;
      box-shadow: inset 2px 4px 2px rgba(0, 0, 0, 0.25);
      border-radius: 50%;
    }
    .active {
      background-color: white;
    }
  }
}
</style>