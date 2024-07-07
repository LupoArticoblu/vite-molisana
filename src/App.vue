<template>
  <!--3 usiamo i componenti-->
  <!-- Per vedere la props creata in header, la passiamo come proprietà.
  (INIZIA IN HEADER.VUE)... E QUI, NEL COMPONENTE FIGLIO UTILIZZIAMO LE PROPS COME ATTRIBUTI-->
  <Header saluto="Props: Ciao, sono header" :menu="menu"/>
  <Main />
  <Footer />
  <div>Sono app</div>
</template>

<script>
//1 importiamo i 3 componenti
import Header from './components/header.vue';
import Main from './components/main.vue';
import Footer from './components/footer.vue';
export default {
  name: 'App',
  data() {
    return {
      //cicliamo il menù (in app.vue per dimostrare l'utilità delle props) ATTENZIONE: LE PROPS CHE PASSO TRAMITE DATA VANNO INSERITE NEI TAG COL BINDING
      menu: [
        {
          name: 'Home',
          link: '#',
          current: true
        },
        {
          name: 'Prodotti',
          link: '#',
          current: false
        },
        {
          name: 'Chi siamo',
          link: '#',
          current: false
        },
        {
          name: 'Contatti',
          link: '#',
          current: false
        }
      ] 
    }
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
