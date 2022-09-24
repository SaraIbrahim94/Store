<template>
    <div class="cart-drawer_container">
        <div class="bg-overlay hide"></div>
        <div class="cart-drawer hide_drawer">
            
            <div class="cart-drawer_header">
                <a @click="closeDrawer" class="close"><img src="../assets/icon-close.svg" alt="close-icon"></a>
                <div class="cart-title"> <h4>Your Cart</h4></div>
            </div>

            <div class="cart-drawer_body">
                <p class="cart-drawer_empty-text">Your Cart is Empty</p> 
            </div>

            <div class="cart-drawer_footer">
                <button type="submit" class="checkout_btn">Checkout</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'cartDrawer',
        methods:{
            closeDrawer: function closeDrawer(){
               let drawerElem = document.querySelector('.cart-drawer_container');
               drawerElem?.querySelector('.cart-drawer').classList.add('hide_drawer');
               drawerElem?.querySelector('.bg-overlay').classList.add('hide');
            }
        }
    }
</script>

<style lang="scss" scoped>
    .cart-drawer{
        display: block;
        height: 100%;
        position: fixed;
        bottom: 0;
        width: 40%;
        z-index: 100;
        top: 0;
        background-color: white;
        right: 0;
        transition: transform 1s ease-in-out;
        overflow: hidden;
        display: flex;
        flex-direction: column;
        justify-content: space-between;

        @media screen and (max-width:1150px){
            width: 80%;
        }

        @media screen and (max-width:550px){
            width: 85%;
        }

        &.hide_drawer{
            transform: translateX(1000px);
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

        .cart-drawer_header{
            margin: 0 0 3rem 0;
            padding-top: 2rem;

            .cart-title{
                border-bottom: 1px solid black;
                padding-left: 3rem;
    
                h4{
                    font-size: 2rem;
                    font-weight: 500;
                    letter-spacing: .15rem;
                    margin: 0 0 1rem 0;
                    font-family: system-ui;
                    text-transform: uppercase;
                }
            }
        }

        .cart-drawer_body{
            height: 40vw;
            display: flex;
            align-items: center;
            justify-content: center;

            .cart-drawer_empty-text{
                text-align: center;
                font-size: 2rem;
                font-family: sans-serif;
            }
        }

        .cart-drawer_footer{
            display: flex;
            margin: 2rem 0;

            .checkout_btn{
                display: block;
                width: 100%;
                background-color: black;
                color: white;
                text-transform: uppercase;
                padding: 2rem 1rem;
                cursor: pointer;
                font-size: 2rem;
                letter-spacing: .3rem;

                &:hover{
                    background-color: rgb(42, 40, 40);
                }
            
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