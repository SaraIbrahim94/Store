<template>
    <div class="header">

      <div class="logo">
        <img src="@/assets/logo.jpeg" alt="logo">
      </div>

      <nav class="nav-menu mediun-hide small-hide">
          <li><a href="#">SHOP</a></li>
          <li><a href="#">BAGS</a></li>
          <li><a href="#">RINGS</a></li>
          <li><a href="#">ABOUT</a></li>
      </nav>

      <div class="header-icons">
        <a v-on:click="openDrawer" class="cart-icon icon">
          <img src="@/assets/icon_favorite.png" alt="favorite-products" width="45" height="45" >
        </a>

        <a v-on:click="openMenuDrawer" class="menu-icon icon large-hide">
          <img src="@/assets/icon-hamburger.svg" alt="icon-menu" width="35" height="25">
        </a>
    </div>
    </div>
    
</template>

<script>
export default{
      name: 'HeaderComponent',
      data (){},
      methods: {
        openDrawer: function openDrawer() {
          let drawerElem = document.querySelector('.cart-drawer_container');
          drawerElem?.querySelector('.cart-drawer').classList.remove('hide_drawer');
          drawerElem?.querySelector('.bg-overlay').classList.remove('hide');
        },
        openMenuDrawer: function openMenuDrawer(){
          let drawerElem = document.querySelector('.menu-drawer_container');
          console.log(drawerElem);
          drawerElem?.querySelector('.menu-drawer').classList.remove('hide_drawer');
          drawerElem?.querySelector('.bg-overlay').classList.remove('hide');
        }
      },
  }

</script>

<style lang="scss" scoped>
  .header{
    display: flex;
    justify-content: flex-start;
    align-items: center;
    background: #f7cac9;
    justify-content: space-between;

    .header-icons{
      display: flex;

      .icon{
        margin-right: 2rem;
      }

      .menu-icon{
        display: flex;
      align-items: center;
      }
    }

    .logo{
      width: 10%;

      img{
        max-width: 100px;
        height: auto;
        mix-blend-mode: multiply;
      }
    }

    .nav-menu{
      display: flex;
      justify-content: center;
      width: 80%;

      li{
        max-width: 30%;
        margin-right: 40px;
        list-style: none;
        
        a{
          text-decoration: none;
          color: black;
          font-weight: 700;
          font-size: 2rem;
          font-family: sans-serif;
          letter-spacing: .2rem;
          cursor: pointer;
        }
      }
    }

    .cart-icon{
      cursor: pointer;
    }
   
  }
</style>