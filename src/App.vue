<template>
  <div id="app">
    <div v-if="flagLoader" class="spinner-container">
      <div class="spinner-border text-light" style="width: 3rem; height: 3rem;" role="status"></div>
    </div>
    <div v-if="flagAlert" class="alert-container">
      <div class="alert">No results for your query.</div>
    </div>
    <Header @search="searchMovie" />
    <Main :movies="moviesList" :searchedMovie="searchedMovie" @back="searchMovie" />
  </div>
</template>

<script>
import axios from "axios";
import Header from '@/components/Header.vue'
import Main from '@/components/Main.vue'

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
      flagLoader: false,
      flagAlert: false
    }
  },
  created() {
    this.searchMovie("popular", "")
  },
  methods: {
    searchMovie: function(searchType, searchedElement) {
      this.flagLoader = true;
      this.flagAlert = false;  
      this.moviesList = [];
      if (searchType == "multi" && searchedElement.trim().length === 0) {
        this.flagLoader = false;
        this.flagAlert = true;
        this.searchedMovie = "";
      } else {
        this.searchedMovie = searchedElement;
        axios
        .get(
          `https://api.themoviedb.org/3/${this.searchUrl(searchType)}${searchedElement}`
        )
        .then((response) => {
          if (response.data.results.length === 0 && response.data.results.length === null) {
            this.flagLoader = false;
            this.flagAlert = true;
          } else {
            this.flagLoader = false;
            this.moviesList = response.data.results;
          }
        });
      }
    },
    searchUrl: function(searchType) {
      if (searchType == "popular") {
        return "trending/all/week?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it";
      }
      if (searchType == "multi") {
        return "search/multi?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it&query=";
      }
    }
  }
}
</script>

<style lang="scss">
@import "./style/app.scss";
</style>