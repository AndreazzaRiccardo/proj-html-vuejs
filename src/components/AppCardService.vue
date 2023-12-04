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

    img {
        max-width: 100%;
    }
}
</style>
