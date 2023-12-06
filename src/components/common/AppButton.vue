<script>
export default {
  props: {
    textButton: String,
    background: Boolean,
    color: String
  },
  methods: {
    showSection(text) {
      if (text === "GET IN TOUCH") {
        return '#get-in-touch'
      }
    }
  }
}
</script>

<template>
  <button :class="{ 'bg': background }">
    <a :class="`${color}`" :href="showSection(textButton)">{{ textButton }}</a>
  </button>
</template>

<style lang="scss" scoped>
@use "../../style/partials/mixins" as *;
@use "../../style/partials/variables" as *;

button {
  background-color: transparent;
  border: 1px solid $primary-green;
  padding: .5rem 1rem;
  cursor: pointer;
  border-radius: 3px;

  @include responsive ("lg") {
    font-size: .7rem;
    text-wrap: nowrap;
  }

  &.bg {
    background-color: $primary-green;
    border: none;
  }

  .green {
    color: $primary-green;
  }

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
