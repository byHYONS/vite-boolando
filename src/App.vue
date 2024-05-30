<script>
import HeaderComponent from './components/HeaderComponent.vue';
import CardComponent from './components/CardComponent.vue';
import FooterComponent from './components/FooterComponent.vue';

export default {
  name: 'AppBoolando',
  data(){
    return{

    }
  },
  components: {
    HeaderComponent,
    CardComponent,
    FooterComponent,
  },
  methods: {

  }

}




</script>

<!-- HTML -->
<template>
  <HeaderComponent />

  <CardComponent />

  <FooterComponent />
</template>


<style lang="scss">

</style>