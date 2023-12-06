<script>
export default {
    methods: {
        getImg(img) {
            return new URL(`../assets/img/${img}.jpg`, import.meta.url).href
        }
    },
    props: {
        cardContent: Object
    }
}
</script>

<template>
    <div class="card-service">
        <img :src="getImg(cardContent.imgUrl)" alt="Service Image">
        <h4>{{ cardContent.title }}</h4>
        <p>{{ cardContent.text }}</p>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.card-service {
    padding: 1.5rem 2.5rem;
    background-color: $white-bg;
    width: calc((100% - 2rem) / 3);
    border-radius: 5px;
    @include flex (column, flex-start, flex-start);
    gap: 1rem;

    @include responsive ("lg") {
        width: calc((100% - 1rem) / 2);
        align-self: stretch;
        margin-top: 2rem;
    }

    @include responsive ("md") {
        padding: 1rem 1.5rem;
    }

    img {
        max-width: 100%;
    }
}
</style>
