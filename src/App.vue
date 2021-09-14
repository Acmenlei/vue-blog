<template>
  <basic-layout />
</template>

<script lang="ts">
import BasicLayout from "./layout/basic-layout.vue";
import { queryUserList } from "./api/user";

export default {
  name: "App",
  components: { BasicLayout },
  setup() {
    queryUserList().then((res) => {
      console.log(res);
    });
  },
};
</script>
<style lang="scss">
// 全局样式
* {
  box-sizing: border-box;
  &::before,
  &::after {
    box-sizing: border-box;
  }
}
body {
  background: #f8f8f8;
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
}
</style>
