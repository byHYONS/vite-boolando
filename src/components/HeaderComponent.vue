<script>

// importo info menu:
import menuHeader from '../data/menu.json';

// istanza Vue:
export default{
    name: 'HeaderComponent',
    data(){
        return{
            menuHeader,
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
                        <li v-for="(menu, index) in menuHeader.menuItem" 
                        :key="index">
                        <a :href="`#${menu.toLocaleLowerCase()}`" >{{ menu }}</a>
                        </li>
                    </ul>
                </div>
                <!-- LOGO -->
                <div class="col-33 logo">
                    <a :href="`#${menuHeader.menuItem[0].toLocaleLowerCase()}`">
                        <img :src="menuHeader.logoImage" alt="logo" class="logo-img">                        
                    </a>
                </div>
                <!-- ICONE -->
                <div class="col-33 social">
                    <img v-for="(socialIcon, index) in menuHeader.socialIcons" 
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
@use '../scss/partials/header-variables' as *;

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
