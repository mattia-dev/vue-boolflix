<template>
  <div id="app">
    <Header @search="searchMovie" />
    <Main :movies="moviesList" :searchedMovie="searchedMovie" :flagLoader="flagLoader" :flagAlert="flagAlert" :flagDefault="flagDefault" :flagResults="flagResults" @back="searchMovie" />
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
      flagAlert: false,
      flagDefault: true,
      flagResults: false
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
          if (response.data.results.length === 0) {
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
        this.flagDefault = true;
        this.flagResults = false;
        return "trending/all/week?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it";
      }
      if (searchType == "multi") {
        this.flagDefault = false;
        this.flagResults = true;
        return "search/multi?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it&query=";
      }
    }
  }
}
</script>

<style lang="scss">
@import "./style/app.scss";
</style>