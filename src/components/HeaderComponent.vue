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
    <div class="d-flex jc-between ai-center">
        <div class="coll-33"> 
            <!-- LINK: UOMO, DONNA E BAMMBINO -->
            <ul>
                <li><a href="#" class="gender">Uomo</a></li>
                <li><a href="#" class="gender mx-10">Donna</a></li>
                <li><a href="#" class="gender">Bambino</a></li>
            </ul>
        </div>
        <!-- LOGO -->
        <div class="coll-33 logo">
            <img src="./img/boolean-logo.png" alt="logo" class="logo-img">
        </div>
        <!-- ICONE -->
        <div class="coll-33 ta-right">
            <img src="./img/facebook_6422199.svg" alt="icona" class="header-icons">
            <img src="./img/twitter_6422210.svg" alt="icona" class="header-icons mx-25">
            <img src="./img/instagram_6422200.svg" alt="icona" class="header-icons mx-10">
        </div>
    </div>
    
</template>


<!-- STYLE -->
<style lang="sass" scoped>

</style>