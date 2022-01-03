<template>
  <div>
      <h2>Serie TV</h2>
      <ul>
          <li v-for="(serie, index) in series" :key="index">
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

</style>