<template>
  <span>Sono main</span>
  <main>
    <div class="container cards">
      <!-- questo sarà il genitore di productCard, il main, in cui passiamo i props come attributi del tag/componente-->
      <ProductCard 
        v-for="(card, index) in products" 
        :key="index" 
        :image="card.src" 
        :cardTitle="card.titolo"
      />

    </div>
  </main>
</template>

<script>
//importo i prodotti
import products from '../data/prod'
//importo productcard
import ProductCard from './ProductCard.vue'
export default {
  name: 'main',
  components: {
    //lo aggiungo fra i componenti
    ProductCard
  },
  data() {
    return {
      products
    }
  }
}
</script>

<style lang="scss" scoped>
  main{
    padding: 50px 0;
    background-image: url('../assets/grano.webp');
    min-height: 500px;
  }
  
  .cards{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
</style>