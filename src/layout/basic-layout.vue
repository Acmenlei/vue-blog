<template>
  <header-bar />
  <div class="basic-layout">
    <router-view />
    <slider-bar class="slider-bar" />
  </div>
</template>

<script>
import SliderBar from "./slider-layout.vue";
import HeaderBar from "./header-layout.vue";
export default {
  name: "basic-layout",
  components: { SliderBar, HeaderBar },
};
</script>

<style lang='scss' scoped>
.basic-layout {
  display: flex;
  padding-top: 1rem;
  justify-content: center;
  .slider-bar {
    flex: 0.58;
    margin-left: 1rem;
    background: #000;
  }
}
</style>