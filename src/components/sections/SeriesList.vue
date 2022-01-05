<template>
  <div class="container">
      <h2>Serie TV</h2>
      <ul>
          <li v-for="(serie, index) in series" :key="index" class="item">
              <Card :info="serie"/>
          </li>
      </ul>
  </div>
</template>

<script>
import Card from "../elements/Card.vue";

export default {
    name: "SeriesList",
    components: {
        Card
    },
    props: {
        series: Array
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/partials/variables.scss";
.item {
    width: calc(100% / 6);
    color: $text-white;
}
</style>