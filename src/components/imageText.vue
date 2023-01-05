<template>
    <div class="image-text_container">

        <div class="media">
            <picture>
                <source
                sizes="(max-width: 608px) 100vw, 608px"
                srcset="
                    @/assets/ring-work.jpeg 1920w,
                    @/assets/ring-work.jpeg 1280w,
                    @/assets/ring-work.jpeg  640w,
                    @/assets/ring-work.jpeg  320w
                "
                type="image/jpeg"
                />
                <!-- snip lots of other stuff -->
                <img loading="lazy" />
            </picture>
        </div>

        <div class="content">
            <h3>Bure work</h3>
            <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
                when an unknown printer took a galley of type and scrambled it to make a type specimen book.</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'imageText'
    }
</script>

<style lang="scss" scoped>
    .image-text_container{
        display: flex;
        margin: 8rem 0;

        @media screen and (max-width: 749px){
            flex-direction: column;
            margin: 4rem 0;
        }

        .media{
            width: 50%;

            @media screen and (max-width: 749px){
                width: 100%;
            }

            img{
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
        }

        .content{
            width: 50%;
            padding-left: 2rem;
            display: flex;
            flex-direction: column;
            justify-content: center;

            @media screen and (max-width: 749px){
                width: 100%;
            }

            h3{
                letter-spacing: 2px;
                font-family: cursive;
                text-transform: uppercase;
                font-size: 2.8rem;
                margin-bottom: .5rem;
            }

            p{
                max-width: 80%;
                line-height: 1.5;
                font-size: 1.4rem;
            }
        }
       
    }
</style>