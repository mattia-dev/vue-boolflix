<template>
    <div>
        <div class="card-container row flex-nowrap">
         <!-- v-for="(moviesList, index) in movies" :key="index" -->
         
            <div class="movie-container col" v-for="movie in movies" :key="movie.id">
                <div class="movie" :style=createBackground(movie)>
                    <div class="movie-details d-flex justify-content-center align-items-center">
                        <div>
                            <div v-if="movie.title !== undefined" class="title">{{movie.title}} - {{movie.original_title}}</div>
                            <div v-if="movie.name !== undefined" class="title">{{movie.name}} - {{movie.original_name}}</div>
                            <div class="language">Original language: {{movie.original_language}}</div>
                            <div class="rating">Average rating: <span :style=movieRating(movie)>{{movie.vote_average}}</span></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- <div class="card-container row flex-nowrap">
            <div class="movie-container col" v-for="movie in movies2" :key="movie.id">
                <div class="movie" :style=createBackground(movie)>
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

        <div class="card-container row flex-nowrap">
            <div class="movie-container col" v-for="movie in movies3" :key="movie.id">
                <div class="movie" :style=createBackground(movie)>
                    <div class="movie-details d-flex justify-content-center align-items-center">
                        <div>
                            <div class="title">{{movie.title}} - {{movie.original_title}}</div>
                            <div class="language">Original language: {{movie.original_language}}</div>
                            <div class="rating">Average rating: <span :style=movieRating(movie)>{{movie.vote_average}}</span></div>
                        </div>
                    </div>
                </div>
            </div>
        </div> -->
    </div>
</template>

<script>

export default {
  name: 'Card',
  props: {
    movies: Array,
    // movies2: Array,
    // movies3: Array
  },
  data() {
    return {
        "baseUrl": 'https://image.tmdb.org/t/p/original',
    }
  },
  methods: {
    createBackground: function(movie) {
        if (movie.poster_path != null) {
            return `background-image:url("${this.baseUrl}${movie.poster_path}")`;
        } else {
            return "background-color:black";
        }
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
    overflow: auto;
    padding: 36px 6px;

    &:hover .movie-container {
        transform: translateX(-4%);
    }

    .movie-container {
        padding: 0 6px;
        transition: transform 500ms;
        position: relative;
  

        &:hover {
        transform: scale(1.08);
        z-index: 1;
        }

        &:hover ~ .movie-container {
            transform: translateX(4%);
        }
        
        &:hover .movie {
            transform: scale(1.08);
        }

    }

    .movie {
        height: 500px;
        width: 310px;
        background-size: cover;
        background-position: center;
        cursor: pointer;
        transition: transform 500ms;

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
            transition: .2s;

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