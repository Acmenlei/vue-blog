<template>
  <div class="header-layout">
    <label class="label" for="toggle">
      &#9776;
      <p class="header-layoutigator">navgation</p>
    </label>
    <input type="checkbox" id="toggle" />
    <div class="menu">
      <a href="#" class="a">Article List</a>
      <a href="#" class="a">LeaveWord</a>
      <a href="#" class="a"><search-bar /></a>
      <a href="#" class="a">Login</a>
    </div>
  </div>
</template>

<script>
import SearchBar from "../components/searchBar/index.vue";
export default {
  name: "header-layout",
  components: { SearchBar },
};
</script>

<style lang='scss' scoped>
$b: #1b1b1b;
$f: #fff;
.header-layout {
  border-bottom: 1px solid #eaeaea;
  text-align: center;
  height: 70px;
  line-height: 70px;
  background: $f;
}
.menu {
  .a {
    z-index: 3;
    position: relative;
    clear: right;
    text-decoration: none;
    color: #433f3f;
    background: #fff;
    padding: 10px 30px;
    line-height: 30px;
    border-bottom: red;
    &:hover {
      color: #b81818;
      border-bottom: 2px solid #b81818;
    }
    &:nth-child(3):hover {
      border-bottom: none;
    }
  }
}

.label {
  margin: 0 40px 0 0;
  font-size: 26px;
  line-height: 22px;
  display: none;
  color: #433f3f;
  float: right;
  width: 180px;
}
.header-layoutigator {
  display: inline-flex;
  font-size: 25px;
}
#toggle {
  display: none;
}

@media only screen and (max-width: 700px) {
  .menu {
    text-align: center;
    width: 100%;
    display: none;
    .a {
      display: block;
      border-bottom: 1px solid #eaeaea;
      margin: 0;
      font-size: 20px;
    }
  }
  .label {
    display: block;
    cursor: pointer;
  }
  #toggle:checked + .menu {
    display: block;
  }
}
@media only screen and (max-width: 600px) {
  .header-layoutigator {
    display: none;
  }
  .label {
    margin: 0 40px 0 0;
    font-size: 28px;
    line-height: 70px;
    color: grey;
    float: right;
    width: 26px;
    float: right;
  }
}
</style>