<script>
import AppButton from './AppButton.vue';
export default {
  components: { AppButton }
}
</script>

<template>
  <section>
    <div class="container">
      <div class="title">
        <p>NEWSLETTER</p>
        <h4><span>Know</span> First</h4>
        <p>Follow closely and receive content about our company and the news of the current market.</p>
      </div>
      <form action="">
        <label for="name"><input placeholder="Name" type="text" id="name"></label>
        <label for="e-mail"><input placeholder="Email" type="email" id="e-mail"></label>
        <AppButton :textButton="'SUBSCRIBE'" :background="true"/>
      </form>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

section {
  min-height: 350px;
  background-image: url(../assets/img/bg-1.jpg);
  background-position: center;
  background-size: cover;
  @include flex;

  .container {
    @include flex;
    gap: 1rem;

    form {
      @include flex(column, center, flex-start);
      gap: 1rem;

      input {
        min-width: 250px;
        min-height: 30px;
        background-color: rgba($color: $white-bg, $alpha: .6);
        border: none;
        padding: 0 .5rem;
        outline: none;
        border-radius: 3px;
      }
    }

    .title {
      color: $white-bg;
      width: 50%;
      @include flex(column, space-between, flex-start);
      gap: 1rem;

      p {
        font-size: .9rem;
        color: $primary-green;

        &:last-child {
          color: $adv-bg;
        }
      }

      h4 {
        font-size: 2rem;

        span {
          background-color: rgba($color: $primary-green, $alpha: .3);
          padding: .2rem .5rem;
        }
      }
    }
  }


}
</style>
