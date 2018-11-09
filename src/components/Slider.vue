<template>
<div classs="carousel">
    <slide v-for="(slide, index) in slides" v-if="index == currentComponent" :key="index" :image="slide.image">
    </slide>
    <navigation v-for="(slide, index) in slides" :key="slide.text">
        <button @click="currentComponent = index">{{ index + 1 }}</button>
    </navigation>
    <button @click="next"> Next</button>
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
      currentComponent: "0",
      intervalID: ""
    };
  },
  props: ["slides", "delay", "autoplay", "loop"],
  components: {
    Slide,
    Navigation
  },
  methods: {
      next() {
          if (this.currentComponent == this.$props.slides.length - 1) {
              this.currentComponent = 0;
          } else {
              this.currentComponent++;
          }
      }
  },
  created: function() {
      this.intervalID = setInterval(this.next, this.$props.delay);
  }
};
</script>

