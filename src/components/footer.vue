<template>
  <span>Sono footer</span>
  <footer>
    <div class="cols container">
      <div class='logo'>
        <img src="/public/Logo.png" alt="">
      </div>
      <div class="links">
        <h4>Menù</h4>
        <nav>
          <ul>
            <!-- centralizzando le informazioni nel file menù posso riutilizzarle ovunque nei componenti-->
            <li v-for="(link, index) in menu" :key="index"><a :href="link.link">{{ link.name }}</a></li>
          </ul>
        </nav>
      </div>    
      <div class="links">
        <h4>Pastificio</h4>
        <nav>
          <ul>
            <li><a href="#">Il Pastificio</a></li>
            <li><a href="#">Grano</a></li>
            <li><a href="#">Filiera</a></li>
            <li><a href="#">100 anni di pasta</a></li>
            <li><a href="#">Sartoria della pasta</a></li>
          </ul>
        </nav>
      </div>
      <div class="links">
        <h4>Prodotti</h4>
        <nav>
          <ul>
            <li><a href="#">Le classiche</a></li>
            <li><a href="#">Le integrali</a></li>
            <li><a href="#">Le speciali</a></li>
            <li><a href="#">Le biologiche</a></li>
            <li><a href="#">Le senza glutine</a></li>
          </ul>
        </nav>
      </div>
    </div>
    <div class="foot-img">
      <!-- percorso statico 
      <img src="../assets/footer.jpg" alt="">
      -->
      <!-- percorso dinamico -->
      <img :src="getImg(footerImg)" alt="">
    </div>
    <button @click="store.count++" style="background-color: #adb210"> incrementa il contatore store esportato in App.vue</button>
  </footer>
</template>

<script>
import menu from '../data/menu';
//importo store
import { store } from '../data/store';
export default {
  name: 'footer',
  data() {
    return {
      footerImg: 'footer.jpg',
      menu,
      store
    }
  },
  methods: {
    getImg(imgName) {
      //ATTENZIONE QUESTA FORMULA PERMETTE DI CREARE UNA URL DINAMICA OER INSERIRE IMMAGINI
      return new URL(`../assets/${imgName}`, import.meta.url).href
    },
  },
}
</script>

<style lang="scss" scoped>
  @use '../Style/partials/mixin' as *;
  @use '../Style/partials/variabili' as *;
  footer{
    padding: 30px 0;
    overflow-x: hidden;
    .cols{
      display: flex;
      .links{
        h4{
          text-transform: uppercase;
          font-size: 1.2rem;
          margin-bottom: 20px;
        }
        ul{
          list-style: none;
          li{
            a{
              display: inline-block;
              text-decoration: none;
              color: black;
              font-size: 0.9rem;
              margin-bottom: 6px;
              &:hover{
                color: $primary-color;
              }
              &:focus{
                background-color: lighten($primary-color, 70%);
              }
            }
          }
        }
        margin-left: 150px;
        padding: 0 30px;
      }    
      .logo{
        img{
          width: 200px;
        }
      }
    }
    .foot-img{
      position: relative;
      overflow: hidden;
      width: 100%;
      img{
        position: relative;
        left: -260px;
        min-width: 130%;
        height: 200px;
        
      }
    }
  }
</style>