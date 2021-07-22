<template>
  <main>
    <div class="search-result d-flex align-items-center">
      <div v-if="flag == 'Results for: '" class="arrow-container d-flex align-items-center" @click="$emit('search', trending, searchedElement)">
        <i class="fas fa-arrow-left"></i>   
      </div>

      <h2>{{flag}}<span v-if="flag == 'Results for: '">"{{searchedMovie}}"</span></h2>
    </div>

    <div v-if="flagLoader" class="spinner-container">
      <div class="spinner-border text-light" style="width: 3rem; height: 3rem;" role="status"></div>
    </div>

    <div v-if="flagAlert" class="alert-container">
      <div class="alert">No results for your query.</div>
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
    flagLoader: Boolean,
    flagAlert: Boolean,
    flags: Array
  },
  data() {
    return {
      trending: "trending/all/week?api_key=250bb34c3a8ad3b342c86dd16717b4d8&language=it",
      searchedElement: "",
    };
  },
  computed: {
    flag: function () {
        let flags = this.flags.filter(function (flag) {
          return flag.status == true;
        });
        return flags[0].name;
    }
  }
}
</script>

<style lang="scss" scoped>
@import "../style/app.scss";

main {
  height: 100%;
  margin-top: 36px;
  padding: 0 12px;
  position: relative;

  h2 {
    color: $text-primary;
  }

  .search-result {
    margin-bottom: 8px;
    height: 40px;

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

  .spinner-container {
    display: flex;
    justify-content: center;
    align-items: center;
    top: 5%;
  }

  .alert-container {
    display: flex;
    justify-content: center;
    align-items: center;
    top: 5%;

    .alert {
      text-align: center;
      font-size: 24px;
      font-weight: 500;
      color: $text-white;
      margin: 0;
      padding: 0;
    }
  }
}
</style>