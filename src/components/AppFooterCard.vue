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
        <ul>
            <li v-for="link in cardText.links" :key="cardText.title">
                <a href=""><i class="fa-solid fa-angle-right"></i> {{ link }}</a>
            </li>
        </ul>

    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.card {
    background-color: rgba($color: $adv-bg, $alpha: .1);
    padding: 1.5rem;
    border-radius: 10px;

    ul {
        list-style-type: none;

        li {
            margin-bottom: .5rem;
        }
    }

    h5 {
        font-size: 1.5rem;
        color: $white-bg;
        margin-bottom: .5rem;
    }

    a {
        text-decoration: none;
        color: $adv-bg;
        font-size: .8rem;
        text-wrap: nowrap;

        i {
            margin-right: .5rem;
        }
    }
}
</style>
