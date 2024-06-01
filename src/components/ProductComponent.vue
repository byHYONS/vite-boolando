<script>

// import component:
import CardComponent from './CardComponent.vue';

// import file products:
import products from '../data/products.json';
import products2 from '../data/db.json';

export default {
   name: 'ProductComponent',
   data(){
      return{
        products,
        products2,
      }
   },
   components: {
        CardComponent,
   },
   methods: {
    
   }
}

</script>

<!-- HTML -->
<template>
    
    <div class="col-33" 
    v-for="(product, index) in products" :key="index">
    
        

    </div>


    <main>
        <div class="container">
            <div class="d-flex">
                <div class="col-33" 
                v-for="(product, index) in products" :key="index">

                    <CardComponent 
                    :products="product" />

                </div>
            </div>
        </div>
    </main>
    
</template>


<!-- STYLE -->
<style lang="scss" scoped>

// variabili:
@use '../scss/partials/component-variables' as *;

main {
    background-color: $background;
    margin-top: 100px;
    margin-bottom: 50px;
    width: $width;
    .d-flex {
    display: flex;
    flex-wrap: wrap;
    gap: 15px;
        .col-33 {
        width: calc(100% / 3 - (15px * 2 / 3));
        }
    }
}

</style>
