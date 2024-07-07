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
      products: [
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/1-spaghetto-quadrato.jpg',
          titolo: "N.4 - Spaghettino Quadrato Bucato",
          tipo: 'lunga',
          cottura: '6',
        },
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/5-fettuccine.jpg',
          titolo: "N.5 - Fettuccine",
          tipo: 'lunga',
          cottura: '16', 
        },
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/6-linguine.jpg',
          titolo: "N.6 - Linguine",
          tipo: 'lunga',
          cottura: '14',
        },
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/7-mezze-linguine.jpg',
          titolo: "N.7 - Mezze Linguine",
          tipo: 'lunga',
          cottura: '10',
        },
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/8-linguine-vegana.jpg',
          titolo: "N.8 - Linguine Vegana",
          tipo: 'lunga',
          cottura: '11',
        },
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/11-spaghettino-quadrato.jpg',
          titolo: "N.11 - Spaghettino Quadrato",
          tipo: 'lunga',
          cottura: '9',
        },
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/38-mezze-maniche.jpg',
          titolo: "N.38 - Mezze Maniche",
          tipo: 'corta',
          cottura: '8',
        },
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/44-sedani.jpg',
          titolo: "N.44 - Sedani",
          tipo: 'corta',
          cottura: '12',
        },
        {
          src: 'https://www.lamolisana.it/wp-content/uploads/2021/04/49-sedanini.jpg',
          titolo: "N.49 - Sedanini",
          tipo: 'corta',
          cottura: '10',
        },
        {
          src: "https://www.lamolisana.it/wp-content/uploads/2020/05/1-spaghetti.png",
          titolo: "N.1 - Spaghetti",
          tipo: "Lunga",
          cottura: "10-12 minuti"
        },
        {
          src: "https://www.lamolisana.it/wp-content/uploads/2020/05/2-penne.png",
          titolo: "N.2 - Penne Rigate",
          tipo: "Corta",
          cottura: "11 minuti"
        },
        {
          src: "https://www.lamolisana.it/wp-content/uploads/2020/05/3-fusilli.png",
          titolo: "N.3 - Fusilli",
          tipo: "Corta",
          cottura: "12 minuti"
        },
        {
          src: "https://www.lamolisana.it/wp-content/uploads/2020/05/4-tagliatelle.png",
          titolo: "N.4 - Tagliatelle",
          tipo: "Lunga",
          cottura: "8-10 minuti"
        },
        {
          src: "https://www.lamolisana.it/wp-content/uploads/2020/05/5-lasagna.png",
          titolo: "N.5 - Lasagna",
          tipo: "Larga",
          cottura: "Lasagna al forno"
        },
        {
          src: "https://www.lamolisana.it/wp-content/uploads/2020/05/6-farfalle.png",
          titolo: "N.6 - Farfalle",
          tipo: "Corta",
          cottura: "13 minuti"
        },
        {
          src: "https://www.lamolisana.it/wp-content/uploads/2020/05/7-bucatini.png",
          titolo: "N.7 -Bucatini",
          tipo: "Lunga",
          cottura: "9 minuti"
        }  
      ]
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