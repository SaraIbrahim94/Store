<template>
  <div class="featured-products">
    <carousel :breakpoints='breakpoints'>

        <slide v-for="slide in 10" :key="slide">
          <a href="#">
            <div class="product-card">
              <div class="media-container">
                  <picture>
                      <source
                      sizes="(max-width: 608px) 100vw, 608px"
                      srcset="
                          @/assets/ring_1.jpeg 1920w,
                          @/assets/ring_1.jpeg 1280w,
                          @/assets/ring_1.jpeg  640w,
                          @/assets/ring_1.jpeg  320w
                      "
                      type="image/jpeg"
                      />
                      <img loading="lazy" />
                  </picture>
              </div>

              <div class="product-info">
                <h5>Diamond ring</h5>
                <p>299 $</p>
              </div>
            </div>
          </a>
        </slide>
  
        <template #addons>
          <navigation />
          <pagination />
        </template>
    </carousel>
    </div>
  </template>

<script>
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

export default {
      name: 'FeaturedProducts',
      components: {
      Carousel,
      Slide,
      Pagination,
      Navigation
    },
      data: () => ({
      settings: {
        itemsToShow: 1,
        snapAlign: 'center',
      },
      // any settings not specified will fallback to the carousel settings
      breakpoints: {
        749: {
          itemsToShow: 3,
          snapAlign: 'center',
        }
      },
    }),
  }

</script>

<style lang="scss">
  .featured-products{
    width: 70%;
    margin: auto;

    .carousel{

      .carousel__prev, .carousel__next{
        background-color: transparent;
        color: black;
        transform: scale(2);
      }

      img{
        width: 100%;
        height: 100%;

        @media screen and (max-width: 749px){
          width: 70%;
        }
      }

    }

    a{
      text-decoration: none;
      color: black;
    }
  }
</style>