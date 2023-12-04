<script>
import AppHeader from './components/AppHeader.vue';
import AppServices from './components/AppServices.vue';
import AppAboutCompany from './components/AppAboutCompany.vue';
import AppAdv from './components/AppAdv.vue';
import AppNews from './components/AppNews.vue';
import AppNewsLetter from './components/AppNewsLetter.vue';
import AppFormMessage from './components/AppFormMessage.vue';
import AppFooter from './components/AppFooter.vue';
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
