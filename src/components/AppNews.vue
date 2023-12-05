<script>
import AppButton from './AppButton.vue';
import AppCardNews from './AppCardNews.vue';
export default {
  components: { AppButton, AppCardNews },
  data() {
    return {
      cardsArray: [
        {
          imgPath: "news-1",
          text: "Increasing creativity is possible for everyone"
        },
        {
          imgPath: "news-2",
          text: "Because market research is part of the business plan"
        },
        {
          imgPath: "news-3",
          text: "Working from home is now a trend"
        },
      ]
    }
  }
}
</script>

<template>
  <section>
    <div class="container">
      <div class="news-text">
        <p>OUR EDITORIAL CONTENT</p>
        <h4>Latest <span>News</span></h4>
        <div class="btn-section">
          <p>Every week we publish content about what is best in the business world.</p>
          <AppButton :textButton="'SEE ALL'" />
        </div>
        <div class="cards">
          <AppCardNews v-for="card in cardsArray" :cardContent="card" />
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

section {
  padding: 5rem 0;
}

.news-text {
  &>p {
    color: $primary-green;
    font-weight: bolder;
    font-size: .8rem;
    filter: brightness(120%);
  }

  h4 {
    font-size: 1.8rem;
    margin: 1rem 0;

    span {
      background-color: rgba($color: $primary-green, $alpha: .2);
      color: $primary-green;
      padding: .2rem .5rem;
    }
  }

  .btn-section {
    @include flex(row, space-between);
    margin-bottom: 1.5rem;

    p {
      color: $adv-bg;
      font-size: .9rem
    }
  }

  .cards {
    @include flex;
    gap: 1rem;
  }
}
</style>
