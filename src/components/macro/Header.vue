<template>
  <div class="header">
    <!-- logo -->
    <div class="logo">
      <h1>BOOLFLIX</h1>
    </div>
    <!-- /logo -->

    <!-- navbar -->
    <ul>
      <li>Home</li>
      <li>Serie TV</li>
      <li>Film</li>
      <li>Nuovi e popolari</li>
      <li>La mia lista</li>
      <li>Audio e sottotitoli</li>
    </ul>
    <!-- /navbar -->
    <!-- searchbox -->
    <form @submit.prevent="$emit('search', searchText)">
      <input type="text" placeholder="Titolo film o serie TV" v-model="searchText">
      <button>Cerca</button>
    </form>
    <!-- /searchbox -->
  </div>
</template>

<script>


export default {
    name: 'Header',
    data() {
      return {
        searchText: ""
      }
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/style/global.scss";

</style>