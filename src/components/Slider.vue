<template>
<div classs="carousel">
    <slide v-for="(slide, index) in slides" v-if="index == currentComponent" :key="index" :image="slide.image">
    </slide>
    <navigation v-for="(slide, index) in slides" :key="slide.text">
        <button @click="currentComponent = index">{{ index + 1 }}</button>
    </navigation>
</div>
</template>
<script>
/* eslint-disable */
import Slide from "./Slide.vue";
import Navigation from "./Navigation.vue";

export default {
  name: "Slider",
  data: function() {
    return {
      slides: [
        {
          text: "Slide 1",
          image: "https://dummyimage.com/500x400/000000/fff.jpg&text=Slide+1"
        },
        {
          text: "Slide 2",
          image: "https://dummyimage.com/500x400/000000/fff.jpg&text=Slide+2"
        },
        {
          text: "Slide 3",
          image: "https://dummyimage.com/500x400/000000/fff.jpg&text=Slide+3"
        }
      ],
      currentComponent: "0"
    };
  },
  components: {
    Slide,
    Navigation
  }
};
</script>

