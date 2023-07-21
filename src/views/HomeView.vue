<script setup>
import { useMovieStore } from '../stores/movie'
const movieStore = useMovieStore();

</script>

<template>
    <div class="home">
        <div class="featured-movie-card">
            <router-link  to="/movie/tt0078346">
                <img src="https://m.media-amazon.com/images/M/MV5BMzA0YWMwMTUtMTVhNC00NjRkLWE2ZTgtOWEzNjJhYzNiMTlkXkEyXkFqcGdeQXVyNjc1NTYyMjg@._V1_SX300.jpg" alt="movie-img" class="featured-movie-img">
                <div class="movie-detail">
                    <h3>SuperMan</h3>
                    <p>An alien orphan is sent from his dying planet to Earth, where he grows up to become his adoptive home's first and greatest superhero</p>
                </div>
            </router-link>
        </div>


        <form @submit.prevent="movieStore.SearchMovies" class="search-box">
            <div class="">
                <input type="text" placeholder="Search the movie" v-model="movieStore.search">
                <input type="submit" value="Search">
            </div>
        </form>


        <div class="movies-list">
            <div class="movie" v-for="movie in movieStore.movies" :key="movie.imdbID">
                <router-link :to="{name: 'movie-detail', params: {id: movie.imdbID}}" class="movie-link">
                    <div class="movie-image">
                        <img :src="movie.Poster" alt="">

                        <div class="movie-type">{{ movie.Type }}</div>
                    </div>

                    <div class="movie-detail">
                        <p class="movie-year">{{ movie.Year }}</p>
                        <h3>{{ movie.Title }}</h3>
                    </div>
                
                </router-link>
            </div>
        </div>

    </div>
</template>

