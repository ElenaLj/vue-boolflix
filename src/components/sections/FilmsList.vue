<template>
  <div>
      <h2>Film</h2>
      <ul>
          <li v-for="(film, index) in films" :key="index">
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

</style>