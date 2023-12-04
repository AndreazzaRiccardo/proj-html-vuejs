<script>
import AppLogo from './AppLogo.vue';
import AppButton from './AppButton.vue';
export default {
    components: { AppLogo, AppButton }
}
</script>

<template>
    <header>
        <h2>HEADER TOP</h2>
        <h2>
            HEADER BOTTOM (JUMBO)
        </h2>
    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;
</style>
