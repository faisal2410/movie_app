<script setup>
import { onMounted } from 'vue';
import { useMovieStore } from '../stores/movie'
import { useRoute } from 'vue-router';

const movieStore = useMovieStore();
console.log(movieStore)
const route = useRoute();
console.log(route.params.id)

onMounted(() => {
movieStore.getSingleMovie(route.params.id);
    
})
</script>

<template>
<div class="movie-detail">
    <h3>{{ movieStore.singleMovie.Title }}</h3>
    <p>{{ movieStore.singleMovie.Year }}</p>
    <img :src="movieStore.singleMovie.Poster" alt="" class="movie-image">
    <p>{{ movieStore.singleMovie.Plot }}</p>
</div>

</template>
