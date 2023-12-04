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
  border: 1px solid $primary-green;
  padding: .5rem 1rem;
  cursor: pointer;
  border-radius: 3px;
  background-color: transparent;

  &:hover {
    filter: brightness(120%)
  }

  a {
    text-decoration: none;
    color: $white-bg;
    font-weight: bold;
  }
}
</style>
