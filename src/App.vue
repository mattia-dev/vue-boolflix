<template>
  <div id="app">
    <Header @search="searchMovie" :searchStrings="searchStrings" />
    <Main @search="searchMovie" :movies="moviesList" :searchedMovie="searchedMovie" :flagLoader="flagLoader" :flagAlert="flagAlert" :flags="flags" />
  </div>
</template>

<script>
import axios from "axios";
import dayjs from 'dayjs'
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
      flags: [
        {
          name: "Trending of the week",
          status: false,
        },
        {
          name: "Shows",
          status: false,
        },
        {
          name: "Movies",
          status: false,
        },
        {
          name: "Netflix Originals",
          status: false,
        },
        {
          name: "Recently added",
          status: false,
        },
        {
          name: "Results for: ",
          status: false,
        },
      ],
      searchStrings: [
        {
          name: "trending",
          url: "trending/all/week?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it",
          string: "Home",
        },
        {
          name: "tv",
          url: "discover/tv?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it",
          string: "TV Shows",
        },
        {
          name: "movies",
          url: "discover/movie?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it",
          string: "Movies",
        },
        {
          name: "originals",
          url: "discover/tv?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it&with_networks=213",
          string: "Originals",
        },
        {
          name: "recents",
          url: `discover/tv?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it&first_air_date.gte=${dayjs().subtract(14, 'day').format('YYYY-MM-DD')}`,
          string: "Recently added",
        },
        {
          name: "multi",
          url: "search/multi?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it&query=",
        },
      ]
    }
  },
  created() {
    this.searchMovie(this.searchStrings[0].url, "")
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
      for (let i = 0; i < this.searchStrings.length; i++) {
        if (searchType == this.searchStrings[i].url) {
          this.flags[i].status = true;
        } else {
          this.flags[i].status = false;
        }
      }
      return searchType;
    }
  }
}
</script>

<style lang="scss">
@import "./style/app.scss";
</style>