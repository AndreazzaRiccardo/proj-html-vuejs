<script>
import AppCardAboutCompany from './AppCardAboutCompany.vue';
export default {
  methods: {
    getImg(img) {
      return new URL(`../assets/img/${img}.jpg`, import.meta.url).href
    }
  },
  data() {
    return {
      attributeArray: [
        {
          title: "Leadership",
          value: "0%"
        },
        {
          title: "Psychology",
          value: "0%"
        },
        {
          title: "Flexibility",
          value: "1%"
        }
      ]
    }
  },
  components: { AppCardAboutCompany }
}
</script>

<template>
  <section>
    <div class="decoration top">
      <p v-for="n in 36">.</p>
    </div>
    <div class="text">
      <p>ABOUT THE NETWORK</p>
      <h2><span>The</span> Company</h2>
      <p>With all of this expertise and capability comes an unrivalled commitment to customer service.</p>
      <AppCardAboutCompany v-for="card in attributeArray" :cardContent="card" />
    </div>
    <img :src="getImg('about-5')" alt="">
    <div class="decoration bottom">
      <p v-for="n in 36">.</p>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

section {
  background-color: $dark-bg;
  @include flex;
  position: relative;

  .decoration {
    display: flex;
    flex-wrap: wrap;
    width: 150px;
    position: absolute;
    height: 30px;

    &.top {
      top: -51px;
    }

    &.bottom {
      bottom: 21px;
    }

    p {
      width: calc(100% / 9);
      color: rgba($color: $primary-green, $alpha: .3);
      font-size: 70px;
      line-height: 15px;
    }
  }

  .text {
    width: calc(75% / 2);
    margin-left: auto;
    color: $white-bg;
    padding-right: 3rem;

    h2 {
      margin-bottom: 1rem;

      span {
        background-color: rgba($color: $primary-green, $alpha: .3);
        display: inline-block;
        padding: .1rem .5rem;
      }
    }

    p {

      color: $adv-bg;

      &:first-child {
        color: $primary-green;
        font-size: .5rem;
        margin-bottom: 1rem;
      }
    }

  }

  img {
    width: 50%;
  }
}
</style>
