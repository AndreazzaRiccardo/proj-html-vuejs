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
  components: { AppHeader, AppServices, AppAboutCompany, AppAdv, AppNews, AppNewsLetter, AppFormMessage, AppFooter}
}
</script>

<template>
  <AppHeader />
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
@use "./style/general.scss";
@use "@fortawesom/fontawesome-free/css/all.css";


</style>
