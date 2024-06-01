<script>

// importo info menu:
import menuFooter from '../data/footer.json';

// istanza Vue:
export default {
   name: 'FooterComponent',
   data(){
      return{
        menuFooter,
      }
   }
}

</script>


<!-- HTML -->
<template>
    <footer>
        <div class="container">
            <div class="d-flex">
                <!-- nome brand -->
                <div class="col-50">
                    <h3> {{ menuFooter.nameBrand }} </h3>
                    <div class="">
                        <ul class="policy">
                            <!-- policy -->
                            <li v-for="(policy, index) in menuFooter.menuItem" 
                            :key="index">
                            <a :href="`#${policy.toLocaleLowerCase()}`" >{{ policy }}</a>
                        </li>
                        </ul>
                    </div>
                </div>
                <div class="col-50 social">
                    <!-- social -->
                    <h5> {{ menuFooter.messageSocial }} </h5>
                    <img v-for="(socialIcon, index) in menuFooter.socialIcons" 
                    :key="index" :src="socialIcon.image" 
                    :alt="socialIcon.name">
                </div>
            </div>
        </div>
    </footer>
    
</template>

<!-- STYLE -->
<style lang="scss" scoped>

// variabili:
@use '../scss/partials/footer-variables' as *;


footer {
    font-family: "Ubuntu", sans-serif;
    width: $width;
    justify-content: center;
    align-content: center;
    height: $height;
    background-color: $background;
    border-top: 2px solid $borderTop;
    h3 {
        margin-bottom: 8px;
        color: $colorText;

    }
}

.d-flex {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.col-50 {
    width: calc(100% / 2);
}

.policy {
    display: flex;
    a {
        margin-right: 10px;
        font-size: 12px;
        color: $colorText;
        text-decoration: none;
        transition: 0.5s;
        &:hover {
            color: $borderTop;
        }
    }
    li {list-style-type: none;}

}

.social {
    text-align: end;
    h5 {
        color: $colorText;
        margin-bottom: 10px;
    }
    img {
        padding-left: 10px;
        width: 7%;
        filter: invert(100%);
        cursor: pointer;
        transition: 0.3s;
        &:hover {
            transform: scale(150%);
        }
    }
}

</style>
