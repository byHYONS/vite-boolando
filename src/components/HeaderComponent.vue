<script>

// importo info menu:
const menuHeader = ['Uomo', 'Donna', 'Bambino'];
const socialIcons = [
    {
        image: '../../public/img/facebook_6422199.svg',
        name: 'Facebook Icon'
    },
    {
        image: '../../img/twitter_6422210.svg',
        name: 'Twitter Icon'
    },
    {
        image: '../../img/instagram_6422200.svg',
        name: 'Istagram Icon'
    }
];

// istanza Vue:
export default{
    name: 'HeaderComponent',
    data(){
        return{
            menuHeader,
            socialIcons,
            image: '../../img/boolean-logo.png',
        }
    }
}


</script>

<!-- HTML -->
<template>

    <header>
        <div class="container">
            <div class="d-flex">
                <div class="col-33"> 
                    <!-- LINK MENU -->
                    <ul class="gender">
                        <li v-for="(menu, index) in menuHeader" 
                        :key="index">
                        <a :href="`#${menu.toLocaleLowerCase()}`" >{{ menu }}</a>
                        </li>
                    </ul>
                </div>
                <!-- LOGO -->
                <div class="col-33 logo">
                    <a :href="`#${menuHeader[0].toLocaleLowerCase()}`">
                        <img :src="image" alt="logo" class="logo-img">                        
                    </a>
                </div>
                <!-- ICONE -->
                <div class="col-33 social">
                    <img v-for="(socialIcon, index) in socialIcons" 
                    :key="index" :src="socialIcon.image" 
                    :alt="socialIcon.name">
                </div>
            </div>
        </div>
    </header>
    
</template>


<!-- STYLE -->
<style lang="scss" scoped>

// variabili:
$background: #F06837;
$colorText: #fff;
$colorText2: #000;
$shodow: 0 0 10px rgba(0, 0, 0, 0.3);


header {
    background-color: $background;
    position: fixed;
    left: 0;
    top: 0;
    width: 100vw;
    height: 60px;
    z-index: 100;
    box-shadow: $shodow;
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

.col-33 {
    width: calc(100% / 3);
}

.social {
    text-align: right;
    img {
        padding-left: 10px;
        width: 9%;
        filter: invert(100%);
        cursor: pointer;
        transition: 0.3s;
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
        color: $colorText;
        font-family: "Ubuntu", sans-serif;
        font-size: 18px;
        text-decoration: none;
        transition: 0.5s;
        &:hover{
            color: $colorText2;
            text-transform: uppercase;
        }
    }
}

.logo{
    text-align: center;
    a {text-decoration: none;}
    img {
        width: 60%;
    }
}

</style>
