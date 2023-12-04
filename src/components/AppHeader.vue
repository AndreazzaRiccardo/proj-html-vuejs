<script>
import AppLogo from './AppLogo.vue';
import AppButton from './AppButton.vue';
import AppButtonNoBg from './AppButtonNoBg.vue';
export default {
    components: { AppLogo, AppButton, AppButtonNoBg },
    data() {
        return {
            headerMenu: ["HOME", "SERVICES", "SKILLS", "PARTNERS", "BLOG"]
        }
    },
    methods: {
        getImg() {
            return new URL("../assets/img/jumbo.jpg", import.meta.url).href
        },
    }
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
                        <a href=""><i class="fa-brands fa-facebook-f"></i></a>
                    </p>
                    <p>
                        <a href=""><i class="fa-brands fa-twitter"></i></a>
                    </p>
                    <p>
                        <a href=""><i class="fa-brands fa-linkedin-in"></i></a>
                    </p>
                </div>
            </div>
        </div>
        <div class="header-bottom">
            <img :src="getImg()" alt="">
            <div class="container">
                <div class="top">
                    <AppLogo />
                    <div class="menu">
                        <a v-for="item in headerMenu" href="">{{ item }}</a>
                        <AppButton :textButton="'GET IN TOUCH'" />
                    </div>
                </div>
                <div class="bottom">
                    <h2><span>Logistics</span> that goes further.</h2>
                    <p>For 20 years working with the most innovative in the field of transport.</p>
                    <div class="btns">
                        <AppButton :textButton="'GET IN TOUCH'" />
                        <AppButtonNoBg :textButton="'READ MORE'" />
                    </div>
                </div>
            </div>

        </div>
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

                a {
                    color: $adv-bg;
                }
            }
        }
    }
}

.header-bottom {
    min-height: 600px;
    padding: 1.5rem 0;
    position: relative;
    overflow: hidden;

    img {
        position: absolute;
        filter: brightness(50%);
        left: 0;
        top: 0;
        width: 100%;
        height: auto
    }
    
    .container {
        @include flex (column);
        gap: 6rem;

        .top {
            @include flex(row, space-between);
            position: relative;
            width: 100%;

            .menu {
                a {
                    text-decoration: none;
                    color: $white-bg;
                    margin: 0 1rem;

                    &:hover {
                        filter: brightness(80%)
                    }
                }
            }
        }

        .bottom {
            align-self: flex-end;
            position: relative;
            color: $white-bg;
            @include flex (column, flex-end, flex-start);
            gap: 1rem;
            width: 40%;

            h2 {
                font-size: 3.5rem;

                span {
                    position: relative;

                    &::before {
                        position: absolute;
                        content: "";
                        display: inline-block;
                        bottom: 10%;
                        left: 0;
                        background-color: rgba($color: $primary-green, $alpha: .5);
                        width: 100%;
                        height: 40%;
                    }
                }
            }

            p {
                color: rgb(219, 219, 219);
            }

            .btns {
                @include flex ();
                gap: 1rem;
            }
        }
    }
}
</style>
