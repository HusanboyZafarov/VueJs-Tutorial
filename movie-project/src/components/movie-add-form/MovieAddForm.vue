<template>
    <div class="movie-add-form">
        <h1>Yangi kino qo'shish</h1>
        <form action="" class="add-form d-flex gap-3" @submit.prevent>
            <input type="text" class="form-control new-movie-label" placeholder="Qanday kino?" :value="name"
                @input="name = $event.target.value" />
            <input type="text" class="form-control new-movie-label" placeholder="Nechi marotaba ko'rilgan?"
                :value="viewers" @input="viewers = $event.target.value" />
                
            <button class="btn btn-outline-dark" type="submit" @click="addMovie">Qo'shish</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: "",
            viewers: "",
        }
    },
    methods: {
        addMovie(e) {
            const newMovie = {
                name: this.name,
                viewers: this.viewers,
                favourite: false,
                like: false,
                id: Date.now(),
            }
            if (this.name && this.viewers) {
                this.$emit("createMovie", newMovie)
                this.name = ""
                this.viewers = ""
            }
        }
    }
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