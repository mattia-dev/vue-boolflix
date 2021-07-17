<template>
    <div class="card-container">
        <div class="row flex-nowrap">
            <div class="movie" v-for="movie in movies" :key="movie.id" :style=createBackground(movie)>
                <div class="movie-details d-flex justify-content-center align-items-center">
                    <div>
                        <div class="title">{{movie.title}} - {{movie.original_title}}</div>
                        <div class="language">Original language: {{movie.original_language}}</div>
                        <div class="rating">Average rating: <span :style=movieRating(movie)>{{movie.vote_average}}</span></div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'Card',
  props: {
    movies: Array
  },
  data() {
    return {
        "baseUrl": 'https://image.tmdb.org/t/p/original',
    }
  },
  methods: {
    createBackground: function(movie) {
        return `background-image:url("${this.baseUrl}${movie.poster_path}")`;
    },
    movieRating: function(movie) {
        if (movie.vote_average < 6) {
            return `color:#ed553b`;
        } else {
            return `color:#3caea3`;
        }
    }
  }
}
</script>

<style lang="scss" scoped>
@import "../style/app.scss";

::-webkit-scrollbar {
    display: none;
}

.card-container {
    padding-left: 12px;
    overflow: auto;

    .movie {
        height: 500px;
        width: 310px;
        margin-right: 6px;
        padding: 0;
        background-size: cover;
        cursor: pointer;

        &:hover .movie-details {
            visibility: visible;
            background-color: rgba(0, 0, 0, .5);
        }
        
        .movie-details {
            height: 100%;
            width: 100%;
            padding: 0 12px;
            text-align: center;
            font-size: 18px;
            color: $text-primary;
            visibility: hidden;
            transition: background-color .2s;

            .title {
                font-size: 28px;
                font-weight: 500;
                color: $text-white;
                margin-bottom: 12px;
            }

            .language {
                margin: 6px 0;
            }

            .rating {
                span {
                    font-weight: 500;
                }
            }
        }
}
}
</style>