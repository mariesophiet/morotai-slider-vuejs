<template>
<div classs="carousel">
  <transition name="fade" mode="out-in">
    <slide v-for="(slide, index) in slides" v-if="index == currentComponent" :key="index" :image="slide.image">
    </slide>
  </transition>
    <navigation v-for="(slide, index) in slides" :key="slide.text">
        <button @click="currentComponent = index; clear();">{{ index + 1 }}</button>
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
      if (this.$props.loop) {
        if (this.currentComponent == this.$props.slides.length - 1) {
          this.currentComponent = 0;
        } else {
          this.currentComponent++;
        }
      } else {
        if (this.currentComponent < this.$props.slides.length - 1) {
          this.currentComponent++;
        }
      }
    },
    clear() {
      clearInterval(this.intervalID);
    }
  },
  created: function() {
    if (this.$props.autoplay) {
      this.intervalID = setInterval(this.next, this.$props.delay);
    }
  }
};
</script>

<style>
.fade-enter {
  opacity: 0;
}

.fade-enter-active {
  transition: opacity 1s;
}

.fade-leave-active {
  transition: opacity 1s;
  opacity: 0;
}


</style>

