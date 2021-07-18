<template>
  <div id="app">
    <Header @search="searchMovie" />
    <Main :movies="moviesLists" />
  </div>
</template>

<script>
import axios from "axios";
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      moviesLists: [[], [], []],
    }
  },
  created() {
    for (let i = 0; i < 3; i++) {
      axios
      .get(
        "https://api.themoviedb.org/3/movie/popular?api_key=250bb34c3a8ad3b342c86dd16717b4d8&page=" + (i + 1)
      )
      .then((response) => {
        this.moviesLists[i] = response.data.results;
      });
    }
  },
  methods: {
    searchMovie: function(searchedMovie) {
      for (let i = 0; i < 3; i++) {
        this.moviesLists[i] = [];
        axios
        .get(
          "https://api.themoviedb.org/3/search/movie?api_key=250bb34c3a8ad3b342c86dd16717b4d8&query=" + searchedMovie + "&page=" + (i + 1)
        )
        .then((response) => {
          this.moviesLists[i] = response.data.results;
        });
      }
    }
  }
}
</script>

<style lang="scss">
@import "./style/app.scss";
</style>