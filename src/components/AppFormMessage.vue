<script>
import AppButton from './AppButton.vue';
import AppButtonNoBg from './AppButtonNoBg.vue';
export default {
  components: { AppButton, AppButtonNoBg }
}
</script>

<template>
  <section>
    <div class="container">
      <div class="send-message" id="get-in-touch">
        <p>SEND A MESSAGE</p>
        <h4>Get in <span>Touch</span></h4>
        <p>We will respond to your message as soon as possible.</p>
        <div class="form">
          <label for="name"><input required type="text" id="name" placeholder="Name"></label>
          <label for="e-mail"><input required type="email" id="e-mail" placeholder="Email"></label>
          <label for="phone"><input required type="number" id="phone" placeholder="Phone"></label>
          <select for="info">
            <option value="">More info</option>
          </select>
          <label for="message"><textarea required id="message" placeholder="Message"></textarea></label>
        </div>
        <AppButton :textButton="'SEND'" />
      </div>
      <div class="contacts">
        <h6>Example Inc.</h6>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        <p>Sit ipsam itaque ex eum earum, quisquam corporis inventore iusto.</p>
        <a href="">
          <i class="fa-solid fa-phone"></i> + 1 (305) 1234-5678
        </a>
        <a href="">
          <i class="fa-solid fa-envelope"></i> hello@example.com
        </a>
        <a href="">
          <i class="fa-solid fa-location-dot"></i> Main Avenue, 987
        </a>
        <AppButtonNoBg :textButton="'VIEW MAP'" />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

section {
  background-color: $light-bg;
  padding: 4rem 0;

  .container {
    @include flex(row, flex-start, flex-start);
    gap: 2rem;

    .send-message {
      width: 70%;
      @include flex(column, flex-start, flex-start);
      gap: 1.3rem;

      .form {
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;

        label,
        select {
          width: calc((100% - 1rem) / 2);
          min-height: 35px;


          &:last-child {
            width: 100%;
            height: 150px;
          }
        }

        input,
        textarea {
          width: 100%;
          height: 100%;
          background-color: rgba($color: $adv-bg, $alpha: .2);
          border: none;
          padding: 0 .5rem;
          outline: none;
          border-radius: 3px;
          font-family: inherit;
          resize: none;
        }

        textarea {
          padding: .5rem .5rem;
        }

        select {
          background-color: rgba($color: $adv-bg, $alpha: .2);
          border: none;
          outline: none;
          padding: 0 .2rem;
          color: $adv-bg;

          option {
            font-size: 1.5rem;
          }
        }


      }

      h4 {
        font-size: 2rem;

        span {
          background-color: rgba($color: $primary-green, $alpha: .3);
          color: $primary-green;
          padding: .2rem .5rem;
        }
      }

      p {
        color: $adv-bg;
        font-size: .8rem;
        font-weight: bold;
        filter: brightness(120%);

        &:first-child {
          color: $primary-green;
        }
      }
    }

    .contacts {
      width: 30%;
      @include flex(column, flex-start, flex-start);
      gap: 1.3rem;

      h6 {
        font-size: 1rem;
      }

      p {
        font-size: .8rem;
        color: $adv-bg;
      }

      a {
        color: $primary-green;
        text-decoration: none;

        i {
          margin-right: 1rem;
          height: 35px;
          width: 35px;
          border-radius: 50%;
          background-color: rgba($color: $primary-green, $alpha: .2);
          vertical-align: middle;
          text-align: center;
          line-height: 35px;
        }
      }
    }
  }
}
</style>
