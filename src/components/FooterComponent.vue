<template>
    <Footer>
        <div>
            <div class="links">
                <li><a href="#">Shop</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Cookies</a></li>
                <li><a href="#">Our Story</a></li>
                <li><a href="#">Our Vision</a></li>
            </div>

            <div class="social-icons">
                <SociaLicons></SociaLicons>
            </div>
        </div>

        <div class="copy-right">
            © sara-vue
        </div>
    </Footer>
</template>

<script>
    import SociaLicons from './sociaLicons.vue';
    export default {
        name: 'FooterComponenet',
        components: { SociaLicons }
    }
</script>

<style lang="scss">
    footer{
        background-color: #f7cac9;

        > div{
            display: flex;
            padding: 3rem 1rem 1rem 1rem;
            justify-content: space-between;
            align-items: center;
        }

        .links{
            display: flex;

            li{
                margin-right: 1rem;
                list-style: none;               
            }

            a{
                text-transform: uppercase;
                font-size: 1rem;
                font-family: sans-serif;
                font-weight: 500;
                text-decoration: none;
                color: black;

                &:hover{
                    color: rgb(75, 70, 70);
                }
            }
        }

        .social-icons{

            a{
                margin-right: 1rem;

                &:hover{
                    transform: scale(1.5);
                }

                img{
                    width: 22px;
                    height: auto;
                }
            }
        }

        .copy-right{
            align-items: center;
            justify-content: center;
            padding: .5rem;
        }
    }
</style>