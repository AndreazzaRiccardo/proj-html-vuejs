<script>
export default {

}
</script>

<template>
    <div class="logo">
        <strong>
            <span>NEX</span><span>GEN</span>
        </strong>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

strong {
    span:first-child {
        color: $primary-green;
        background-color: rgba($color: $primary-green, $alpha: 0.2);
        padding: .6rem .1rem .6rem 1.5rem;
        border-bottom-left-radius: 60px;
        border-top-left-radius: 60px;
    }
    span:last-child {
        color: rgb(219, 219, 219);
    }
}
</style>
