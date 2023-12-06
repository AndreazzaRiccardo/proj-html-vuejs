<script>
import AppLogo from './AppLogo.vue';
import AppButton from './AppButton.vue';
export default {
    components: { AppLogo, AppButton },
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
                        <a href="https://www.facebook.com/people/Nexgen-Dispatching-LLC/100092162691560/?mibextid=ZbWKwL"><i
                                class="fa-brands fa-facebook-f"></i></a>
                    </p>
                    <p>
                        <a href=""><i class="fa-brands fa-twitter"></i></a>
                    </p>
                    <p>
                        <a href="https://tr.linkedin.com/company/nexgen-logistics"><i
                                class="fa-brands fa-linkedin-in"></i></a>
                    </p>
                </div>
            </div>
        </div>
        <div class="hero">
            <img :src="getImg()" alt="">
            <div class="container">
                <div class="top">
                    <AppLogo />
                    <div class="menu">
                        <ul>
                            <li v-for="item in headerMenu" :key="item"><a href="">{{ item }}</a></li>
                            <li>
                                <AppButton :textButton="'GET IN TOUCH'" :background="true" />
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="bottom">
                    <h2><span>Logistics</span> that goes further.</h2>
                    <p>For 20 years working with the most innovative in the field of transport.</p>
                    <div class="btns">
                        <AppButton :textButton="'GET IN TOUCH'" :background="true" />
                        <AppButton :textButton="'READ MORE'" />
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

    @include responsive ("md") {
        height: auto;
    }

    .container {
        @include flex (row, space-between);

        @include responsive ("lg") {
            font-size: .7rem;
        }

        @include responsive ("md") {
            align-items: flex-start;
        }

        .hour {
            i {
                margin-right: .5rem
            }
        }

        .contacts {
            @include flex;

            @include responsive ("md") {
                flex-wrap: wrap;
                text-wrap: nowrap;
            }

            p {
                margin-left: 1.5rem;

                a {
                    color: $adv-bg;
                }
            }
        }
    }
}

.hero {
    padding: 1.5rem 0 8rem 0;
    position: relative;
    overflow: hidden;


    img {
        position: absolute;
        filter: brightness(50%);
        left: 0;
        top: 0;
        width: 100%;
        height: auto;

        @include responsive ("lg") {
            height: 600px;
            object-fit: cover
        }

        @include responsive ("md") {
            height: 900px;
        }
    }

    .container {
        @include flex (column);
        gap: 6rem;

        .top {
            @include flex(row, space-between);
            position: relative;
            width: 100%;

            @include responsive ("md") {
                flex-direction: column;
            }

            .menu {
                ul {
                    @include flex(row, space-between);
                    list-style-type: none;

                    @include responsive ("md") {
                        flex-direction: column;
                        gap: 1rem;
                        margin-top: 2rem;
                    }
                }

                a {
                    text-decoration: none;
                    color: $white-bg;
                    margin: 0 1rem;
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

            @include responsive ("md") {
                width: 100%;
            }

            h2 {
                font-size: 3.5rem;

                @include responsive ("lg") {
                    font-size: 2.5rem;
                }

                span {
                    display: inline-block;
                    background-color: rgba($color: $primary-green, $alpha: 0.5);
                    height: 30px;
                    line-height: 5px;
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
