<template>
  <div class="card">
    <img :src="image" :alt=" cardTitle ">
    <h3>{{ cardTitle }}</h3>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props: {
    image: String,
    cardTitle: String,
  }
  //props: ['image', 'cardTitle'] <- altro modo di scrivere le props, solo che non si capisce di che tipo siano così
}
</script>

<style lang="scss" scoped>
  @use '../Style/partials/variabili' as *;
  .card{
    flex-basis: 25%;
    background-color: white;
    border: 2px solid lighten($primary-color, 73%);
    min-height: 200px;
    padding: 15px;
    text-align: center;
  }
</style>