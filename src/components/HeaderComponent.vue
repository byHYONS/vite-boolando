<script>
export default{
    name: 'HeaderComponent',
    data(){
        return{

        }
    }
}


</script>

<!-- HTML -->
<template>
    <div class=" menu-fixed">
        <div class="container">
            <div class="d-flex">
                <div class="coll-33"> 
                    <!-- LINK: UOMO, DONNA E BAMMBINO -->
                    <ul class="gender">
                        <li><a href="#" >Uomo</a></li>
                        <li><a href="#" >Donna</a></li>
                        <li><a href="#" >Bambino</a></li>
                    </ul>
                </div>
                <!-- LOGO -->
                <div class="coll-33 logo">
                    <img src="../../img/boolean-logo.png" alt="logo" class="logo-img">
                </div>
                <!-- ICONE -->
                <div class="coll-33 social">
                    <img src="../../public/img/facebook_6422199.svg" alt="icona">
                    <img src="../../img/twitter_6422210.svg" alt="icona">
                    <img src="../../img/instagram_6422200.svg" alt="icona">
                </div>
            </div>
        </div>
    </div>
    
</template>


<!-- STYLE -->
<style lang="scss" scoped>

.menu-fixed {
    background-color: #F06837;
    position: fixed;
    left: 0;
    top: 0;
    width: 100vw;
    height: 60px;
    z-index: 100;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
    align-content: center;
}

.container {
    width: 70%;
    margin: 0 auto;
}

.d-flex {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.coll-33 {
    width: calc(100% / 3);
}

.social {
    text-align: right;
    img {
        padding-left: 10px;
        width: 9%;
        filter: invert(100%);
        cursor: pointer;
        transition: 0.5s;
        &:hover {
            transform: scale(150%);
    }
    }
}

.gender {
    li  {
        list-style-type: none;
        padding-right: 15px;
        display: inline-block;
        list-style-type: none;
    }
    a  {
        text-decoration: none;
        color: white;
        font-family: "Ubuntu", sans-serif;
        font-size: 18px;
        text-decoration: none;
        &:hover{
            text-transform: uppercase;
        }
    }
}

.logo{
    text-align: center;
    img {
        width: 60%;
    }
}

</style>