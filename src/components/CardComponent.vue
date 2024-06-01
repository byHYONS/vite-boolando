<script>
export default {
    name: 'CardComponent',
    props: {
        products: String,
    },
    setup() {
        
    },
}
</script>


<template>
    
    <div class="card">
        <div class="images">
            <!-- foto di default -->
            <img  class="defoult-img"
            :src="products.image" 
            :alt="products.brand">
            <!-- foto hover -->
            <img  class="hover-img"
            :src="products.image2" 
            :alt="products.brand">
            
            <!-- sconto -->
            <div class="discount">
                <span :class="{'percent': products.discount}">
                    {{ products.discount }}
                </span>
                <!-- sostenibilità prodotto -->
                <span :class="{'tenability': products.sustainability}">
                    {{ products.sustainability ? `sostenibilit&agrave;` : '' }}
                </span>
            </div>
            <!-- liks -->
            <div class="heart">
                <span
                :class="{'favorite': products.isInFavorites}"
                >&hearts;
                </span>
            </div>
        </div>
        <div class="text">
            <!-- nome brand -->
            <span class="brand">{{ products.brand }}</span>
            <!-- descrizione prodotto -->
            <h4>{{ products.description }}</h4>
            <!-- prezzo -->
            <span class="new-price">{{ products.price }}</span>
            <!-- vecchio prezzo -->
            <span class="old-price">
                {{ products.originalPrice ? products.originalPrice : '' }}
            </span>
        </div>
    </div>

</template>


<style lang="scss" scoped>

@use '../scss/partials/component-variables' as *;

/* MAIN • CARD */
.card {
    &:hover .hover-img {display: inline-block;}
    &:hover .defoult-img {display: none;}
    img {width: 100%;}
    .images {position: relative;}
    .hover-img {display: none;}
    .discount {
        position: absolute;
        left: 5px;
        bottom: 25px;
        font-size: 13px;
    }
    .percent {
        background-color: $percScontBG;
        color: $text1;
        padding: 3px;
        margin-right: 5px;
    }
    .tenability {
        background-color: $sostenBG;
        color: $text1;
        padding: 3px;
        margin-right: 3px;
    }
    .heart {                            // cuore
        position: absolute;
        right: 0;
        top: 25px;
        font-size: 25px;
        background-color: $background;
        padding: 3px 10px;
        span.favorite {color: $text2;}
        // &:hover {color: $text2;}
    }
    .text {margin-bottom: 50px;}        // testo card
    .brand {font-size: 12px;}
    .old-price {
        text-decoration: line-through;
        font-size: 12px;
    }
    .new-price {
    font-weight: 600;
    color: $text2;
    margin-right: 5px;
    font-size: 12px;
    }
}

</style>