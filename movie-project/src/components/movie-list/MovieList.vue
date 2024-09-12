<template>
    <ul class="movie-list list-group">
        <MovieListItem v-for="movie in movies" :movie="movie" :key="movie.name" />
    </ul>
</template>

<script>
import MovieListItem from '../movie-list-item/MovieListItem.vue';

export default {
    components: {
        MovieListItem
    },
    props: {
        movies: {
            type: Array,
            required: true,
        }
    }
}
</script>

<style scoped>
.movie-list {
    margin-top: 2rem;
    padding: 1.5rem;
    background: #fcfaf5;
    border-radius: 4px;
    border: none;
    box-shadow: 15px 15px 15px #00000015;
}
</style>