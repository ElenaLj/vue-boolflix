<template>
  <div>
    <h4>{{info.title || info.name}}</h4>
    <img :src="`https://image.tmdb.org/t/p/w154/${info.poster_path}`" :alt="`${info.original_title || info.original_name}`">
    <h5>{{info.original_title || info.original_name}}</h5>
    <div class="flags">
      <img v-if="flags.includes(info.original_language)" :src="require(`../../assets/img/${info.original_language}.png`)" :alt="info.original_language">
      <img v-else src="../../assets/img/none.png" alt="Flag not available">
    </div>
    <div>{{info.vote_average}}</div>
  </div>
</template>

<script>

export default {
    name: "Card",
    props: {
        info: Object
    },
    data() {
      return {
        flags: [
          "en",
          "es",
          "fr",
          "it"
        ]
      }
    }
}
</script>

<style lang="scss" scoped>
  .flags {
    img {
      width: 30px;
    }
  }
</style>