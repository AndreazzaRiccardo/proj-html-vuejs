<script>
import AppFooterCard from './AppFooterCard.vue';
import AppLogo from './AppLogo.vue';
import AppButton from './AppButton.vue';
export default {
  components: { AppFooterCard, AppLogo, AppButton },
  data() {
    return {
      cardsArray: [
        {
          title: "About",
          links: ["The company", "Istitutional", "Social & Events", "Innovation", "Environment", "Technology"]
        },
        {
          title: "Transport",
          links: ["Industrialized", "Chemicals", "Packaged Liquids", "Construction", "Laminated Wood", "And others"]
        },
        {
          title: "Support",
          links: ["Responsability", "Term of Use", "About Cookies", "Privacy Policy", "Accessibility", "Information"]
        }
      ]
    }
  }
}
</script>

<template>
  <footer>
    <div class="footer-top">
      <div class="container">
        <div class="card">
          <AppLogo />
          <p>A Functional HTML Template for Corporate & Business.</p>
          <a href="">
            <i class="fa-solid fa-phone"></i> + 1 (305) 1234-5678
          </a>
          <a href="mailto:hello@example.com">
            <i class="fa-solid fa-envelope"></i> hello@example.com
          </a>
          <a
            href="https://www.google.com/maps/place/101+3rd+Ave+W,+Bradenton,+FL+34205/@27.496425,-82.563613,14z/data=!4m6!3m5!1s0x88c317d099e271a3:0xdaa0a4ffa890a3da!8m2!3d27.4965394!4d-82.5640846!16s%2Fg%2F11fvb6t3m9?hl=it-IT&entry=ttu">
            <i class="fa-solid fa-location-dot"></i> Main Avenue, 987
          </a>
          <AppButton :textButton="'GET IN TOUCH'" />
        </div>
        <AppFooterCard v-for="item in cardsArray" :key="item.title" :cardText="item" />
      </div>
    </div>
    <div class="footer-bottom">
      <div class="container">
        <p>Enjoy the low price. We are tracking any intention of piracy.</p>
        <p><i class="fa-regular fa-copyright"></i> 2020 NEXGEN is Proudly Powered by <a href="">Codings</a>.</p>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.footer-top {
  background-image: url(../assets/img/bg-10.jpg);
  background-size: cover;
  background-position: center;
  padding: 5rem 0;

  @include responsive ("md") {
    padding: 2rem 0;
  }

  .container {
    @include flex(row, space-between, stretch);
    gap: 1.5rem;

    @include responsive ('lg') {
      flex-wrap: wrap;
    }

    .card {
      @include flex(column, flex-start, flex-start);
      gap: .5rem;
      width: calc((100% - 1.5rem) / 4);

      @include responsive ('lg') {
        &:first-child {
          width: 100%;
          align-items: center;
        }

        width: calc((100% - 3rem) / 3);

        @include responsive ("md") {
          width: 100%;
        }
      }

      a:nth-child(5) {
        margin-bottom: 2rem;
      }

      p {
        color: $adv-bg;
        margin: 1.5rem 0;
        font-size: .8rem;
      }

      a {
        color: $adv-bg;
        text-decoration: none;

        i {
          margin-right: .5rem;
        }

      }
    }
  }
}

.footer-bottom {
  background-color: $dark-bg;
  padding: 2rem 0 .5rem 0;

  .container {
    @include flex(row, space-between, flex-end);
    gap: .5rem;

    p {
      color: $adv-bg;
      font-size: .9rem;

      @include responsive ('lg') {
        font-size: .7rem;
      }

      @include responsive ("md") {
        font-size: .6rem;
      }

      a {
        color: $primary-green;
        text-decoration: none;
      }
    }

  }

}
</style>
