<template>
  <a class="card-link" href="#">
    <article class="card">
      <img class="card-image" :src="image" />
      <div class="card-article-details">
        <h4 class="card-post-category">{{ category }}</h4>
        <h3 class="card-post-title">{{ name }}</h3>
        <p class="card-post-description">{{ desc }}</p>
        <p class="card-post-author">By {{ author }}</p>
      </div>
    </article>
  </a>
</template>
<script>
import { toRefs } from "@vue/reactivity";
import { article } from "./scripts/index.js";
export default {
  name: "home",
  setup() {
    return {
      ...toRefs(article),
    };
  },
};
</script>

<style lang="scss" scoped>
$bg: #eedfcc;
$text: #777;
$black: #121212;
$white: #fff;
$red: #e04f62;
$border: #ebebeb;
$shadow: rgba(0, 0, 0, 0.2);

@mixin transition($args...) {
  transition: $args;
}

#container {
  width: 30rem;
  height: 13.625rem;
}

.card {
  display: flex;
  flex-direction: row;
  background: $white;
  box-shadow: 0 0.1875rem .5rem $shadow;
  border-radius: 0.375rem;
  overflow: hidden;
  width: 100%;
}

.card-link {
  width: 60%;
  position: relative;
  display: block;
  color: inherit;
  text-decoration: none;
  &:hover .card-post-title {
    @include transition(color 0.3s ease);
    color: $red;
  }
  &:hover .card-image {
    @include transition(opacity 0.3s ease);
    opacity: 0.9;
  }
}

.card-image {
  @include transition(opacity 0.3s ease);
  display: block;
  width: 100%;
  object-fit: cover;
}

.card-article-details {
  padding: 1.5rem;
}

.card-post-category {
  display: inline-block;
  text-transform: uppercase;
  font-size: 0.75rem;
  font-weight: 700;
  line-height: 1;
  letter-spacing: 0.0625rem;
  margin: 0 0 0.75rem 0;
  padding: 0 0 0.25rem 0;
  border-bottom: 0.125rem solid $border;
}

.card-post-title {
  @include transition(color 0.3s ease);
  font-size: 1.125rem;
  line-height: 1.4;
  color: $black;
  font-weight: 700;
  margin: 0 0 0.5rem 0;
}

.card-post-author {
  font-size: 0.875rem;
  line-height: 1;
  margin: 1.125rem 0 0 0;
  padding: 1.125rem 0 0 0;
  border-top: 0.0625rem solid $border;
}

@media (max-width: 40rem) {
  #container {
    width: 18rem;
    height: 27.25rem;
  }

  .card {
    flex-wrap: wrap;
  }
}

@supports (display: grid) {
  #container {
    grid-area: main;
    align-self: center;
    justify-self: center;
  }

  .card-image {
    height: 100%;
  }

  .card {
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-template-rows: 1fr;
  }

  @media (max-width: 40rem) {
    .card {
      grid-template-columns: auto;
      grid-template-rows: 12rem 1fr;
    }
  }
}
</style>