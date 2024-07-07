<template>
  <header>
    <!--  INTRODUCIAMO LE PROPS: il concetto di props è quello che un informazione deve esser passara dinamicamente ma dal tag/componente padre (per vederlo passiamo in APP.vue)-->
    <span>{{ saluto }}</span>
    <div class="logo">
      <!-- percorso assoluto perchè l'immagine è in public-->
      <img src="/public/Logo.png" alt="">  
    </div>

    <nav>
      <ul>
        <!-- BISOGNA SEMPRE FARE IL BINDING DELLA KEY UNIQUE-->
        <li v-for="(link, index) in menu" :key="index"><a  :href="link.link">{{ link.name }}</a></li>
        
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'header',
  //nello script inseriamo props, le props possono essere di qualsiasi tipo e dimensione
  props: {
    //key : value (imposto l'elemento figlio a ricevere il dato) QUINDI DEFINIAMO NEL COMPONENTE PADRE(HEADER) IL DATO CHE VOGLIAMO TRASMETTERE...(CONTINUA IN aPP.vue)
    saluto : String,
    //inseriamo il menu
    menu: Array
  },
  //ATTENZIONE LE PROPS SONO READONLY:qundi non posso modificarle
  //created() { this.saluto = 'nuovo testo'} <- questo tornerebbe un errore
  data() {
    return {
     
    }
  }
}
</script>

<style lang="scss" scoped>
//inseriamo la mixin
@use '../Style/partials/mixin' as *;
//inseriamo la variabile
@use '../Style/partials/variabili' as *;

header {
  margin-bottom: 50px;
  text-align: center;
  .logo{
    margin-bottom: 50px;
    img {
      width: 200px;
    }
  }
  ul{
    list-style: none;
    @include center('horizontal');
    a{
      text-decoration: none;
      display: inline-block;
      padding: 1rem;
      color: black;
      font-weight: 700;
      &:hover, 
      &:focus {
        // con scss abbiamo anche una peculiarità, con lighten e darken partendo da un colore x possiamo dargli delle percentuali per renderlo più luminoso o meno
        background-color: lighten($primary-color, 69%);
      }
    }
  }
}
</style>