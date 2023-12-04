<script>
export default {
    props: {
        textButton: String
    }
}
</script>

<template>
  <button>
    <a href="">{{ textButton }}</a>
  </button>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

button {
    background-color: $primary-green;
    border: none;
    padding: .2rem 1rem;
    cursor: pointer;
    border: 1px solid $primary-green;

    a {
        text-decoration: none;
        color: $white-bg;
    }
}

</style>
