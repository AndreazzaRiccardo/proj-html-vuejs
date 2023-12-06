<script>
import AppCardService from './AppCardService.vue';
import AppButton from '../common/AppButton.vue';
export default {
  components: { AppCardService, AppButton },
  data() {
    return {
      attributes: ["Tradition", "Quality", "Security"],
      cardsArray: [
        {
          imgUrl: "gallery-3",
          title: "Technology",
          text: "Focused on developing technology solutions adapted to our client's needs."
        },
        {
          imgUrl: "gallery-5",
          title: "Transport",
          text: "We develop operational strategies to improve logistical efficiency."
        }
      ]
    }
  }
}
</script>

<template>
  <section>
    <div class="container">
      <div class="row">
        <div class="col">
          <div class="card">
            <p>OUR BUSINESS AREAS</p>
            <h3>Logistics Services</h3>
            <p>We are leaders in providing ligistics services with a set of cutting edge technologies and a team of
              experienced and renowned professionals.</p>
            <div class="attributes">
              <span v-for="item in attributes">{{ item }}</span>
            </div>
            <AppButton :textButton="'READ MORE'" :background="true" />
          </div>
          <AppCardService v-for="item in cardsArray" :key="item.imgUrl" :cardContent="item" @getImg="" />
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../../style/partials/mixins" as *;
@use "../../style/partials/variables" as *;

section {
  background-color: $light-bg;
  padding: 150px 0;

  @include responsive ("lg") {
    padding: 100px 0;
  }

  @include responsive ("md") {
    padding: 50px 0;
  }
}

.col {
  @include flex(row, center, stretch);
  gap: 1rem;

  @include responsive ("lg") {
    @include flex(row, center, center, wrap);
  }

  .card {
    width: calc((100% - 2rem) / 3);
    @include flex (column, space-between, flex-start);
    gap: 1rem;
    padding-right: 2rem;

    @include responsive ("lg") {
      width: 100%;
    }

    .attributes {
      span {
        color: $primary-green;
        padding: .5rem;
        background-color: rgba($color: $primary-green, $alpha: 0.2);

        &:nth-child(2) {
          margin: 0 1rem;
        }
      }
    }

    h3 {
      font-size: 2rem;
    }

    p:first-child {
      color: $primary-green;
      font-weight: bolder;
    }
  }
}
</style>
