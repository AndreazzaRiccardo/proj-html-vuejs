<script>
export default {
    props: {
        cardContent: Object
    },
    methods: {
        getImg(img) {
            return new URL(`../assets/img/${img}.jpg`, import.meta.url).href
        },
    }
}
</script>

<template>
    <div class="card">
        <img :src="getImg(cardContent.imgPath)" alt="">
        <p>{{ cardContent.text }}</p>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.card {
    position: relative;
    overflow: hidden;
    width: calc(100% / 3);
    min-height: 300px;
    display: flex;
    padding: 2rem;
    border-radius: 10px;

    img {
        position: absolute;
        filter: brightness(50%);
        left: 0;
        top: 0;
        width: 100%;
        height: auto
    }

    p {
        font-size: 1.3rem;
        position: relative;
        color: white;
        font-weight: bolder;
        text-align: center;
        align-self: flex-end;
    }
}
</style>
