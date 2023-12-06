<script>
import AppHeader from './components/header/AppHeader.vue';
import AppServices from './components/main/AppServices.vue';
import AppAboutCompany from './components/main/AppAboutCompany.vue';
import AppAdv from './components/main/AppAdv.vue';
import AppNews from './components/main/AppNews.vue';
import AppNewsLetter from './components/main/AppNewsLetter.vue';
import AppFormMessage from './components/main/AppFormMessage.vue';
import AppFooter from './components/footer/AppFooter.vue';
export default {
  components: { AppHeader, AppServices, AppAboutCompany, AppAdv, AppNews, AppNewsLetter, AppFormMessage, AppFooter},
  methods: {
    getImg(img) {
            return new URL(`../assets/img/${img}.jpg`, import.meta.url).href
        }
  }
}
</script>

<template>
  <AppHeader @getImg="getImg"/>
  <main>
    <AppServices />
    <AppAboutCompany />
    <AppAdv />
    <AppNews />
    <AppNewsLetter />
    <AppFormMessage />
  </main>
  <AppFooter />
</template>

<style lang="scss">
@use "@fortawesome/fontawesome-free/css/all.css";
@use "./style/general.scss";



</style>
