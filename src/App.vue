<template>
  <div id="app">
    <div class="spinner-container" :class="loaderStatus">
      <div class="spinner-border text-light" style="width: 3rem; height: 3rem;" role="status"></div>
    </div>
    <div class="alert-container" :class="alertStatus">
      <div class="alert">No results for your query.</div>
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
      searchedMovie: "",
      loaderStatus: "hide",
      alertStatus: "hide"
    }
  },
  created() {
    // for (let i = 0; i < 3; i++) {
      this.loaderStatus = "show";
      axios
      .get(
        "https://api.themoviedb.org/3/trending/all/week?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it"
        //  + (i + 1)
      )
      .then((response) => {
        this.loaderStatus = "hide";
        this.moviesList = response.data.results;
      });
    // }
  },
  methods: {
    searchMovie: function(searchedMovie) {
      if (searchedMovie.trim().length > 0) {
        this.loaderStatus = "show";
        this.alertStatus = "hide";
        this.searchedMovie = searchedMovie;
        // for (let i = 0; i < 3; i++) {
          // this.moviesLists[i] = [];
          this.moviesList = [];

          axios
          .get(
            "https://api.themoviedb.org/3/search/multi?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it&query=" + searchedMovie
            //  + "&page=" + (i + 1)
          )
          .then((response) => {
            if (response.data.results.length === 0) {
              this.loaderStatus = "hide";
              this.alertStatus = "show";
            } else {
              this.loaderStatus = "hide";
              this.moviesList = response.data.results;
            }
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