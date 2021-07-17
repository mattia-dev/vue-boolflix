<template>
  <main>
    <h2>ORIGINALI NETFLIX</h2>
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
    movies: Array
  },
}
</script>

<style lang="scss" scoped>
@import "../style/app.scss";

main {
    margin-top: 36px;
    padding-left: 12px;

    h2 {
        color: $text-primary;
        margin-bottom: 18px;
    }
}
</style>