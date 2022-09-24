<template>
  <header>
    <div id="app">
      <HeaderComponent></HeaderComponent>
      <MenuDrawer></MenuDrawer>
      <HeroBanner></HeroBanner>
      <CartDrawer></CartDrawer>
      <FeaturedProducts></FeaturedProducts>
      <FooterComponent></FooterComponent>
    </div>
  </header>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import HeroBanner from './components/HeroBanner.vue';
import CartDrawer from './components/cartDrawer.vue';
import FeaturedProducts from './components/FeaturedProducts.vue';
import MenuDrawer from './components/menuDrawer.vue';
import FooterComponent from './components/FooterComponent.vue';

export default {
    name: 'app',
    components: {
    HeaderComponent,
    HeroBanner,
    CartDrawer,
    FeaturedProducts,
    MenuDrawer,
    FooterComponent
}
}

</script>

<style>
body{
  margin: 0;
}
#app{
  overflow: hidden;
  width: 100%;
  position: relative;
}
@media screen and (min-width: 991px){
  .large-hide{
    display: none !important;
  }
}
@media screen and (max-width: 749px){
  .small-hide{
    display: none !important;
  }
}
@media screen and (min-width: 750px) and (max-width: 990px){
  .mediun-hide{
    display: none !important;
  }
}
</style>