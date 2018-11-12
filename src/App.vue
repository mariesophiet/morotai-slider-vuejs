<template>
  <div id="app">
    <Slider :slides="slides" :delay="delay" :autoplay="autoplay" :loop="loop"/>
  </div>
</template>

<script>
/*eslint-disable*/
import Slider from "./components/Slider.vue";
import Slide from "./components/Slide.vue";

export default {
  name: "App",
  components: {
    Slider,
    Slide
  },
  data: function() {
    return {
      slides: [
        {
          text: "Slide 1",
          image: "https://dummyimage.com/500x200/000000/fff.jpg&text=Slide+1"
        },
        {
          text: "Slide 2",
          image: "https://dummyimage.com/500x200/000000/fff.jpg&text=Slide+2"
        },
        {
          text: "Slide 3",
          image: "https://dummyimage.com/500x200/000000/fff.jpg&text=Slide+3"
        },
        {
          text: "Slide 4",
          image: "https://dummyimage.com/400x200/000000/fff.jpg&text=Slide+4"
        }
      ],
      delay: 5000,
      autoplay: true,
      loop: true
    }
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
