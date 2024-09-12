<template>
    <div class="app-info">
        <p class="fs-3 text-uppercase">Movies: {{ allMoviesCount }}</p>
        <p class="fs-3 text-uppercase">Favourite movies: {{ favouriteMoviesCount }}</p>
    </div>
</template>

<script>
export default {
    props: {
        allMoviesCount: {
            type: Number,
            required: true,
        },
        favouriteMoviesCount: {
            type: Number,
            required: true,
        },
    }
}
</script>

<style scoped>
.app-info {
    margin-top: 2rem;
    padding: 1.5rem;
    background: #fcfaf5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px #00000015;
}
</style>