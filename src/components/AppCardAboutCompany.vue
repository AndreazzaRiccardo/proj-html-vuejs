<script>
export default {
    props: {
        cardContent: Object
    }
}
</script>

<template>
    <div class="card-company">
        <div class="value" :class="{ 'line': cardContent.value == '1%' }">{{ cardContent.value }}</div>
        <div class="text">
            <h6>{{ cardContent.title }}</h6>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit.</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.card-company {
    @include flex(row, flex-start, stretch);
    color: $white-bg;
    margin-top: 3rem;

    .line {
        position: relative;

        &::after {
            content: "";
            position: absolute;
            width: 5px;
            height: 1px;
            background-color: $primary-green;
            left: -10.5%;
        }
    }

    .value {
        height: 30px;
        width: 30px;
        border: 5px solid rgba($color: $adv-bg, $alpha: 0.3);
        border-radius: 50%;
        padding: 1.5rem;
        line-height: 30px;
        @include flex;
    }

    .text {
        @include flex(column, space-between, flex-start);
        margin-left: 1rem;

        h6 {
            font-size: 1rem;
        }

        p {
            color: $adv-bg;
        }
    }
}
</style>
