<template>
  <main>
    <h2 v-if="searchedMovie.trim().length == 0">Most popular of the week</h2>
    <div v-if="searchedMovie.trim().length > 0" class="search-result d-flex align-items-center">
      <div class="arrow-container d-flex align-items-center" @click="$emit('back', popular, searchedElement)">
        <i class="fas fa-arrow-left"></i>   
      </div>

      <h2>Results for: "{{searchedMovie.trim()}}"</h2>
    </div>
    <Card v-if="movies.length > 0" :movies="movies" />
  </main>
</template>

<script>
import Card from '@/components/Card.vue'

export default {
  name: 'Main',
  components: {
    Card
  },
  props: {
    searchedMovie: String,
    movies: Array,
    // movies2: Array,
    // movies3: Array
  },
  data() {
    return {
      popular: "popular",
      searchedElement: ""
    };
  },
}
</script>

<style lang="scss" scoped>
@import "../style/app.scss";

main {
    margin-top: 36px;
    padding: 0 12px;

    h2 {
      color: $text-primary;
    }

    .search-result {
      margin-bottom: 8px;

      .arrow-container {
        padding: 0 6px;
        font-size: 20px;
        color: white;
        cursor: pointer;
      }

      h2 {
        margin: 0;
        padding-left: 6px;
      }
    }
}
</style>