<template>
  <div>
    <h4>{{info.title || info.name}}</h4>
    <img :src="`https://image.tmdb.org/t/p/w154/${info.poster_path}`" :alt="`${info.original_title || info.original_name}`">
    <h5>{{info.original_title || info.original_name}}</h5>
    <div class="flags">
      <img v-if="flags.includes(info.original_language)" :src="require(`../../assets/img/${info.original_language}.png`)" :alt="info.original_language">
      <img v-else src="../../assets/img/none.png" alt="Flag not available">
    </div>
    <div class="ratings" v-for="stars in 5" :key="stars">
      <i class="far fa-star"></i>
    </div>
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
    }, 
    computed: {
      starRating() {
        return Math.ceil(this.info.vote_average / 2);
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

  .ratings {
    i {
      color: red;
    }
  }

</style>