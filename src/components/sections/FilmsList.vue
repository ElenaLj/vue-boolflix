<template>
  <div class="container">
      <h2>Film</h2>
      <ul>
          <li v-for="(film, index) in films" :key="index" class="item">
              <Card :info="film"/>
          </li>
      </ul>
  </div>
</template>

<script>
import Card from "../elements/Card.vue";

export default {
    name: "FilmsList",
    components: {
        Card
    },
    props: {
        films: Array
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";
.item {
    width: calc(100% / 4);
    color: $text-white;
}
</style>