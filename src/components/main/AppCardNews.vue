<script>
export default {
    props: {
        cardContent: Object
    },
    methods: {
        getImg(img) {
            return new URL(`../../assets/img/${img}.jpg`, import.meta.url).href
        }
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
@use "../../style/partials/mixins" as *;
@use "../../style/partials/variables" as *;

.card {
    position: relative;
    overflow: hidden;
    width: calc(100% / 3);
    min-height: 300px;
    padding: 2.5rem;
    border-radius: 10px;
    @include flex(row, center, flex-end);

    img {
        position: absolute;
        filter: brightness(50%);
        left: 0;
        top: 0;
        width: 100%;
        height: auto;

        @include responsive ("lg") {
            height: 100%;
            object-fit: cover;
        }
    }

    p {
        font-size: 1.2rem;
        position: relative;
        color: white;
        font-weight: bolder;
        text-align: center;
        align-self: flex-end;

        @include responsive ("lg") {
            font-size: 1rem;
        }

        @include responsive ("md") {
            font-size: .8rem;
        }
    }
}
</style>
