<template>
  <div id="app">
    <div v-if="moviesList.length == 0" class="spinner-container">
      <div class="spinner-border text-light" style="width: 3rem; height: 3rem;" role="status"></div>
    </div>
    <Header @search="searchMovie" />
    <Main :movies="moviesList" :searchedMovie="searchedMovie" />
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
      moviesList: [],
      searchedMovie: ""
    }
  },
  created() {
    // for (let i = 0; i < 3; i++) {
      axios
      .get(
        "https://api.themoviedb.org/3/trending/all/week?api_key=250bb34c3a8ad3b342c86dd16717b4d8&page=1"
        //  + (i + 1)
      )
      .then((response) => {
        this.moviesList = response.data.results;
      });
    // }
  },
  methods: {
    searchMovie: function(searchedMovie) {
      if (searchedMovie.trim().length > 0) {
        this.searchedMovie = searchedMovie;
        // for (let i = 0; i < 3; i++) {
          // this.moviesLists[i] = [];
          this.moviesList = []
          axios
          .get(
            "https://api.themoviedb.org/3/search/movie?api_key=250bb34c3a8ad3b342c86dd16717b4d8&query=" + searchedMovie
            //  + "&page=" + (i + 1)
          )
          .then((response) => {
            this.moviesList = response.data.results;
          });
        // }
      }
    }
  }
}
</script>

<style lang="scss">
@import "./style/app.scss";
</style>