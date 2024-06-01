<script>
import HeaderComponent from './components/HeaderComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import ProductComponent from './components/ProductComponent.vue';

export default {
  name: 'AppBoolando',
  data(){
    return{

    }
  },
  components: {
    HeaderComponent,
    ProductComponent,
    FooterComponent,
  },
}




</script>

<!-- HTML -->
<template>
  <HeaderComponent />

  <ProductComponent />

  <FooterComponent />
</template>


<style lang="scss">

</style>