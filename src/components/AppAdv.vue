<script>
export default {
  methods: {
    getImg(img) {
      return new URL(`../assets/img/logo-${img}.png`, import.meta.url).href
    },
  }
}
</script>

<template>
  <section>
    <div class="container">
      <img class="more-small" :src="getImg(5)" alt="">
      <img :class="{ 'more-small': n === 5 }" v-for="n in 5" :key="n" :src="getImg(n)" alt="">
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

section {
  background-color: $light-bg;
  padding: 5rem 0;

  .container {
    @include flex(row, space-between);

    .more-small {
      width: 5%;
    }

    img {
      width: 10%;
      filter: invert(60%);
    }
  }
}
</style>
