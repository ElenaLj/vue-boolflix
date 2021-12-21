<template>
  <div id="app">
    <Header @search="searching"/>
    <Main :films="films"/>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/macro/Header.vue';
import Main from './components/macro/Main.vue';
import Footer from './components/macro/Footer.vue';

import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  },
  data(){
    return {
      films: []
    }
  },
  methods: {
    searching(payload){
      axios.get("https://api.themoviedb.org/3/search/movie", {
        params: {
          api_key: "d40cf140c7fba913799810f917bf47cb",
          query: payload,
          language: "it-IT"
        }
      })
      .then((response) => {
        console.log(response.data.results);
        this.films = response.data.results;
      })
      .catch((error) => {
        console.log(error);
      });
    }
  }
}
</script>

<style lang="scss">

</style>
