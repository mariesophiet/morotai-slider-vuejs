<template>
    <div class="slide">
        <img :src="image"/>
        <slot></slot>
    </div>
</template>

<script>
/* eslint-disable */
export default {
  name: "Slide",
  props: ["image"]
};
</script>

<style>
.slide {
  width: 50%;
  /*display: block;*/
  margin-left: auto;
  margin-right: auto;
}
</style>
