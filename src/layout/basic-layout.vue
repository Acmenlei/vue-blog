<template>
  <div class="basic-layout">
    <slide-bar />
    <router-view />
  </div>
</template>

<script>
import SlideBar from "./slider-layout.vue";
export default {
  name: "basic-layout",
  components: { SlideBar },
};
</script>

<style lang='scss' scoped>
.basic-layout {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>