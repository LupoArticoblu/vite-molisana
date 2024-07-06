<template>
  <!--3 usiamo i componenti-->
  
  <Header />
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
