<template>
  <div id="app">
    <Slider/>
  </div>
</template>

<script>
/*eslint-disable*/
import Slider from "./components/Slider.vue";
import Slide from "./components/Slide.vue";

export default {
  name: "App",
  components: {
    Slider
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
