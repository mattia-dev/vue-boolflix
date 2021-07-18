<template>
  <main>
    <h2 v-if="searchedMovie.trim().length == 0">Most popoular of the week</h2>
    <h2 v-if="searchedMovie.trim().length > 0">Results for: "{{searchedMovie.trim()}}"</h2>
    <Card :movies="movies" />
  </main>
</template>

<script>
import Card from './Card.vue'

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
}
</style>