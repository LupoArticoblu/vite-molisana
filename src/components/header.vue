<template>
  <span>Sono header</span>
  <header>
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
  data() {
    return {
     //cicliamo il menù
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