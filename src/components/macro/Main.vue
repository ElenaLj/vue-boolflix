<template>
  <div class="main">
    <FilmsList :films="films"/>
    <SeriesList :series="series"/>
  </div>
</template>

<script>
import FilmsList from '../sections/FilmsList.vue';
import SeriesList from '../sections/SeriesList.vue';

export default {
    name: 'Main',
    components: {
      FilmsList,
      SeriesList
    },
    props: {
      films: Array,
      series: Array
    }
}
</script>

<style lang="scss" scoped>
.main {
  height: 100vh;
  background-image: url(../../assets/img/boolflix-background.jpeg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  overflow-y: scroll;
}

</style>