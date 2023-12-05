<script>
export default {
    props: {
        cardText: Object
    }
}
</script>

<template>
    <div class="card">
        <h5>{{ cardText.title }}</h5>
        <a v-for="link in cardText.links" :key="cardText.title" href=""><i class="fa-solid fa-angle-right"></i> {{ link
        }}</a>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.card {
    background-color: rgba($color: $adv-bg, $alpha: .1);
    padding: 1.5rem;
    border-radius: 10px;

    h5 {
        font-size: 1.5rem;
        color: $white-bg;
        margin-bottom: .5rem;
    }

    a {
        font-size: .8rem;
        text-decoration: none;
        color: $adv-bg;

        i {
            margin-right: .5rem;
        }
    }
}
</style>
