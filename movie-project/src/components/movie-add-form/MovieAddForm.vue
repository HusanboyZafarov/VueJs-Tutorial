<template>
    <div class="movie-add-form">
        <h1>Yangi kino qo'shish</h1>
        <form action="" class="add-form d-flex gap-3">
            <input type="text" class="form-control new-movie-label" placeholder="Qanday kino?">
            <input type="text" class="form-control new-movie-label" placeholder="Nechi marotaba ko'rilgan?">
            <button class="btn btn-outline-dark" type="submit">Qo'shish</button>
        </form>
    </div>
</template>

<script>
export default {

}
</script>

<style>
.movie-add-form {
    margin-top: 2rem;
    padding: 1.5rem;
    background: #fcfaf5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px #00000015;
}
</style>