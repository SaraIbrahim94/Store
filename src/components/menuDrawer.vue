<template>
    <div class="menu-drawer_container">
        <div class="bg-overlay hide"></div>
        <div class="menu-drawer hide_drawer">
            
            <div class="menu-drawer_header">
                <a @click="closeDrawer" class="close"><img src="../assets/icon-close.svg" alt="close-icon"></a>
                <img src="@/assets/logo.jpeg" alt="logo">
            </div>

            <div class="menu-drawer_body">
                <nav class="nav-menu">
                    <li><a href="#">SHOP</a></li>
                    <li><a href="#">BAGS</a></li>
                    <li><a href="#">RINGS</a></li>
                    <li><a href="#">ABOUT</a></li>
                </nav>
            </div>

            <div class="menu-drawer_footer">
                <SociaLicons></SociaLicons>
            </div>
        </div>
    </div>
</template>

<script>
import SociaLicons from './sociaLicons.vue';
    export default {
    name: "menuDrawer",
    methods: {
        closeDrawer: function closeDrawer() {
            let drawerElem = document.querySelector(".menu-drawer_container");
            drawerElem?.querySelector(".menu-drawer").classList.add("hide_drawer");
            drawerElem?.querySelector(".bg-overlay").classList.add("hide");
        }
    },
    components: { SociaLicons }
}
</script>

<style lang="scss" scoped>
    .menu-drawer{
        display: block;
        height: 100%;
        position: fixed;
        bottom: 0;
        width: 40%;
        z-index: 100;
        top: 0;
        background-color: white;
        left: 0;
        transition: transform 1s ease-in-out;
        overflow: hidden;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;

        @media screen and (max-width:1150px){
            width: 80%;
        }

        @media screen and (max-width:550px){
            width: 85%;
        }

        &.hide_drawer{
            transform: translateX(-1000px);
            transition: transform 1s ease-in-out;
        }

        .close{
            cursor: pointer;

            img{
                width: 20px;
                height: 20px;
                float: right;
                margin: .3rem 2rem;

                &:hover{
                    transform: scale(1.5);
                    transition: transform 1s ease-in-out;
                }
            }
        }

        .menu-drawer_header{
            margin: 0 0 3rem 0;
            padding-top: 2rem;
            width: 100%;

            img{
              max-width: 140px;
              height: auto;
              mix-blend-mode: multiply;
            }
        }

        .menu-drawer_body{
            height: 100%;
            display: flex;
            align-items: flex-start;
            justify-content: flex-start;
            flex-direction: column;

            .nav-menu{
                display: flex;
                justify-content: center;
                width: 100%;
                flex-direction: column;
          
                li{
                  max-width: 100%;
                  list-style: none;
                  border-bottom: 1px solid black;
                  padding: 2rem 0.4rem .5rem 2rem;
                  
                  a{
                    text-decoration: none;
                    color: black;
                    font-weight: 700;
                    font-size: 2rem;
                    font-family: sans-serif;
                    letter-spacing: .2rem;
                    cursor: pointer;

                    &:hover{
                        color: rgb(75, 70, 70);
                    }
                  }
                }
              }
        }

        .menu-drawer_footer{
            display: flex;
            margin: 2rem 0;
            justify-content: space-around;
            align-items: flex-end;
            border-top: 1px solid black;
            padding-top: 1.5rem;

            a{
                max-width: 25%;
                margin-right: 1.5rem;
            }
        }
    }

    .bg-overlay{
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: rgba(0,0,0,.3);
        top: 0;
        opacity: 1;
        transition: opacity 2s ease-in-out;
        z-index: 99;

        &.hide{
            opacity: 0;
            transition: opacity 1s ease-in-out;
            z-index: -1000;
        }
    }
</style>