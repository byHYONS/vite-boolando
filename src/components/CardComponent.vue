<script>
// import file json:

export default {
   name: 'CardComponent',
   data(){
      return{
        products: [],

      }
   },
   methods: {
    loadProducts() {
            fetch('/products.json')
                .then(response => response.json())
                .then(data => {
                    this.products = data;
                    console.log(data);
                })
                .catch(error => console.error('Error loading JSON:', error));
        }
   },
   created() {
    this.loadProducts()
   },
}

</script>

<!-- HTML -->
<template>

    <main>
        <div class="container">
            <div class="d-flex">
                <div class="col-33" 
                v-for="(product, index) in products" :key="index">
                    <div class="card">
                        <div class="images">
                            <!-- foto di default -->
                            <img  class="defoult-img"
                            :src="product.image" 
                            :alt="product.brand">
                            <!-- foto hover -->
                            <img  class="hover-img"
                            :src="product.image2" 
                            :alt="product.brand">
                            
                            <!-- sconto -->
                            <div class="discount">
                                <span :class="{'percent': product.discount}">
                                    {{ product.discount }}
                                </span>
                                <!-- sostenibilità prodotto -->
                                <span :class="{'tenability': product.sustainability}">
                                    {{ product.sustainability ? `sostenibilit&agrave;` : '' }}
                                </span>
                            </div>
                            <!-- liks -->
                            <div class="heart">
                                <span>&hearts;</span>
                            </div>
                        </div>
                        <div class="text">
                            <!-- nome brand -->
                            <span class="brand">{{ product.brand }}</span>
                            <!-- descrizione prodotto -->
                            <h4>{{ product.description }}</h4>
                            <!-- prezzo -->
                            <span class="new-price">{{ product.price }}</span>
                            <!-- vecchio prezzo -->
                            <span class="old-price">
                                {{ product.originalPrice ? product.originalPrice : '' }}
                            </span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
    
</template>


<!-- STYLE -->
<style lang="scss" scoped>
// variabili:
$background: #fff;

main {
    background-color: $background;
    margin-top: 100px;
    margin-bottom: 50px;
    width: 100vw;
}

.container {
    width: 70%;
    margin: 0 auto;
}

.d-flex {
    display: flex;
    flex-wrap: wrap;
    gap: 15px;
}

.col-33 {
    width: calc(100% / 3 - (15px * 2 / 3));
}


/* MAIN • CARD */
.images {position: relative;}
.card img {width: 100%;}

.hover-img {display: none;}

.card:hover .hover-img {display: inline-block;}
.card:hover .defoult-img {display: none;}

.discount {
    position: absolute;
    left: 5px;
    bottom: 25px;
    font-size: 13px;
}

/* DISCOUNT */
.percent {
    background-color: rgb(237, 58, 52);
    color: white;
    padding: 3px;
}

.tenability {
    background-color: rgb(57, 130, 29);
    color: white;
    padding: 3px;
    margin-right: 3px;
}

/* CUORICINO */
.heart {
    position: absolute;
    right: 0;
    top: 25px;
    font-size: 25px;
    background-color: white;
    padding: 3px 10px;
}

.heart:hover {color: red;}

/* TESTO CARD */
.text {margin-bottom: 50px;}
.brand {
    font-size: 12px;
}

.new-price, .old-price {
    font-size: 12px;
}

.new-price {
    font-weight: 600;
    color: rgb(237, 58, 52);
}

.old-price {text-decoration: line-through;}


</style>