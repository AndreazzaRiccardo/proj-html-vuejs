<script>
import AppLogo from './AppLogo.vue';
import AppButton from './AppButton.vue';
export default {
    components: { AppLogo, AppButton }
}
</script>

<template>
    <header>

        <div class="header-top">
            <div class="container">
                <div class="hour">
                    <p>
                        <i class="fa-solid fa-clock"></i>Open Hours: Mon - Sat - 9:00 - 18:00
                    </p>
                </div>
                <div class="contacts">
                    <p>
                        <i class="fa-solid fa-phone"></i> + 1 (305) 1234-5678
                    </p>
                    <p>
                        <i class="fa-solid fa-envelope"></i> hello@example.com
                    </p>
                    <p>
                        <i class="fa-brands fa-facebook-f"></i>
                    </p>
                    <p>
                        <i class="fa-brands fa-twitter"></i>
                    </p>
                    <p>
                        <i class="fa-brands fa-linkedin-in"></i>
                    </p>
                </div>
            </div>
        </div>
        <h2>
            HEADER BOTTOM (JUMBO)
        </h2>

    </header>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

    .header-top {
        background-color: $header-bg;
        padding: .5rem;
        color: $adv-bg;
        height: 50px;
        @include flex;

        .container {
            @include flex (row, space-between);

            .hour {
                i {
                    margin-right: .5rem
                }
            }
            .contacts {
                @include flex;
                p {
                    margin-left: 1.5rem;
                }
            }
        }
    }
</style>
