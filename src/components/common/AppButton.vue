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
      } else if (text === "VIEW MAP") {
        return "https://www.google.com/maps/place/101+3rd+Ave+W,+Bradenton,+FL+34205/@27.496425,-82.563613,14z/data=!4m6!3m5!1s0x88c317d099e271a3:0xdaa0a4ffa890a3da!8m2!3d27.4965394!4d-82.5640846!16s%2Fg%2F11fvb6t3m9?hl=it-IT&entry=ttu"
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
