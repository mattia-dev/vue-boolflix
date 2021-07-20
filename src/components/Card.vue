<template>
    <div class="main-element">
        <div class="card-container row flex-nowrap">
         <!-- v-for="(moviesList, index) in movies" :key="index" -->
            <div class="movie-container col" v-for="movie in moviesAndShows" :key="movie.id">
                <div class="movie" :style=createBackground(movie)>
                    <div class="movie-details d-flex justify-content-center align-items-center">
                        <div>
                            <div class="media-type">{{mediaType(movie)}}</div>

                            <div class="language d-flex justify-content-center align-items-center">
                                <div class="flag-container">
                                    <img :src="require(`../assets/flags/${movie.original_language.toUpperCase()}.png`)" alt="flag">
                                </div>
                            </div>

                            <div v-if="movie.title !== undefined" class="title">{{movie.title}} - <span class="original-title">{{movie.original_title}}</span></div>
                            <div v-if="movie.name !== undefined" class="title">{{movie.name}} - <span class="original-title">{{movie.original_name}}</span></div>

                            <div class="rating">
                                <i v-for="(star, index) in movieRating(movie)" :key="index" class="fa-star" :class="star"></i>
                            </div>
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
  computed: {
    moviesAndShows: function () {
        return this.movies.filter(function (movie) {
            return movie.original_language !== undefined;
        })
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
        let stars = [];
        let fullStars = Math.round(movie.vote_average / 2);
        for (let i = 1; i <= 5; i++) {
            if (i <= fullStars) {
                stars.push("fas");
            } else {
                stars.push("far");
            }
        }
        return stars;
    },
    mediaType: function(movie) {
        if (movie.media_type == "movie") {
            return "Movie";
        } else {
            return "TV Series";
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

.main-element {
    padding: 0 12px;
}

.card-container {
    overflow: auto;
    padding: 36px 0;

    &:hover .movie-container {
        transform: translateX(-4%);
    }

    .movie-container {
        padding: 0 6px;
        transition: transform .5s;
        position: relative;

        &:first-child {
            padding-left: 0;
        }
  
        &:last-child {
            padding-right: 0;
        }

        &:hover {
            transform: scale(1.08);
            z-index: 1;
        }

        &:first-child:hover {
            transform: translateX(4%);
        }

        &:last-child:hover {
            transform: translateX(-4%);
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
        transition: transform .5s;

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
                line-height: 1.25;
                margin: 6px 0;

                .original-title {
                    font-size: 24px;
                    font-style: italic;
                }
            }

            .language {
                margin-top: 6px;

                .flag-container {

                    img {
                        width: 28px;
                    }
                }
            }

            .rating {
                color: #f6d55c;
                margin-top: 8px;
            }
        }
    }
}
</style>