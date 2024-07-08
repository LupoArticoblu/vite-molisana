<template>
  <!--3 usiamo i componenti-->
  
  <!-- Per vedere la props creata in header, la passiamo come proprietà.
  (INIZIA IN HEADER.VUE)... E QUI, NEL COMPONENTE FIGLIO UTILIZZIAMO LE PROPS COME ATTRIBUTI-->
  <Header saluto="Props: Ciao, sono header" :menu="menu"/>
  <Main />
  <Footer />
  <div>Sono app</div>
  
  <!-- test colori js -->
  <div v-for="(colore, index) in color" :key="index">{{ colore }}</div>
  <!-- test data js-->
  <h5>{{ code }} <span>ecco il codice importato da data</span></h5>
  <h5>{{ getRandomNumber(1,40) }} <span>ecco il numero della funzione random importata da data</span></h5>
  <div class="container">
      <p>contatore: {{ store.count }}</p>
    </div>
</template>

<script>
//importo store
import { store } from './data/store';
//importiamo alcuni dati da data js <- se il file da importare non ha "export default" importo tra le graffe gli elementi che mi servono
import {code, getRandomNumber} from './data/data';
//importo il js colori <- se il file da importare ha "export default" il nome attributo è arbitrario
import color from './data/color';
//importo menù così da poterlo riutilizzare nel footer
import menu from './data/menu';
//1 importiamo i 3 componenti
import Header from './components/header.vue';
import Main from './components/main.vue';
import Footer from './components/footer.vue';
export default {
  name: 'App',
  data() {
    return {
      store,
      //richiamo nei data il js colori
      color,
      //richiamo ciò che ho importato da data js
      code,
      getRandomNumber,

      //cicliamo il menù (in app.vue per dimostrare l'utilità delle props) ATTENZIONE: LE PROPS CHE PASSO TRAMITE DATA VANNO INSERITE NEI TAG COL BINDING
      menu 
    }
  },
  mounted(){
    //metodi
  },
  components: {
    //2 richiamiamoli come proprietà di un oggetto(components) 
    Header,
    Main,
    Footer,
  },
}
</script>

<style lang="scss">
  @use './Style/General';
</style>
