<template>
    <div class="banner">
        <div class="overlay-text">
            <h2>Big Sale on Rings</h2>
            <a href="#">Shop More</a>
        </div>

        <div class="media-img">
            <picture>
                <source
                sizes="(max-width: 608px) 100vw, 608px"
                srcset="
                    @/assets/hero_ring.webp 1920w,
                    @/assets/hero_ring.webp 1280w,
                    @/assets/hero_ring.webp  640w,
                    @/assets/hero_ring.webp  320w
                "
                type="image/jpeg"
                />
                <!-- snip lots of other stuff -->
                <img loading="lazy" />
            </picture>
        </div>
    </div>
</template>

<script>
    export default{
        name: 'HeroBanner'
    }
</script>

<style lang="scss" scoped>
    .banner{
        display: block;
        position: relative;

        img{
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .media-img{
            height: 75vh;

            @media screen and (max-width: 749px){
                height: 70vh;
            }
        }

        .overlay-text{
            position: absolute;
            display: flex;
            background-color: rgba(240,158,157, 0.3);
            animation: 2s fade-in .1s forwards;
            opacity: 0;
            right: 0;
            @media screen and (min-width: 750px){
            top: 40%;
            }
            flex-direction: column;

            @media screen and (max-width: 749px){
                background-color: transparent;
                height: 100%;
                justify-content: flex-end;
                width: 100%;
            }

            h2{
                font-size: 3.5rem;
                font-family: cursive;
                letter-spacing: .5rem;
                margin: 0 2rem;

                @media screen and (max-width: 749px){
                    text-align: center;
                }
            }

            a{
                background-color: black;
                padding: 1.1rem 2rem;
                color: white;
                text-align: center;
                text-decoration: none;
                text-transform: uppercase;
                letter-spacing: .2rem;
                font-family: system-ui;
                font-size: 1.8rem;
                margin: 1rem 2rem;

                &:hover{
                    background-color: rgb(42, 40, 40);
                }
            }
        }
    }
@keyframes fade-in {
    to {
        opacity: 1;
    }
}
</style>