<template>
    <li class="list-group-item d-flex justify-content-between"
        :class="[{ like: movie.like }, { favourite: movie.favourite }]">
        <span class="list-group-item-label" @click="onFavourite">{{ movie.name }}</span>
        <input type="number" class="list-group-item-input" :value="movie.viewers">
        <div class="d-flex justify-content-center align-items-center ">
            <button type="button" @click="onLike" class="btn-cookie btn-sm">
                <i class="fa-solid fa-cookie"></i>
            </button>

            <button type="button" class="btn-trash btn-sm">
                <i class="fa-solid fa-trash"></i>
            </button>

            <i class="fa-solid fa-star"></i>
        </div>
    </li>
</template>

<script>
export default {
    props: {
        movie: {
            type: Object,
            required: true
        }
    },
    methods: {
        onLike() {
            this.$emit('onLike', this.movie.id)
        },

        onFavourite() {
            // this.movie.favourite = this.movie.favourite == true ? false : true
        },
    }
}
</script>

<style scoped>
.list-group-item {
    padding: 15px 20px;
    background: transparent;
    border-bottom: 1px solid #3d5a80;
}

.list-group-item:last-child {
    border-bottom: none;
}

.list-group-item span {
    line-height: 35px;
    font-size: 20px;
    cursor: pointer;
    width: 550px;
}

.list-group-item-input {
    line-height: 35px;
    font-size: 20px;
    text-align: center;
    border: none;
    outline: none;
}

.list-group-item button {
    width: 35px;
    height: 35px;
    margin: 3px;
    font-size: 17px;
    border: none;
    cursor: pointer;
}

.list-group-item .btn-cookie {
    color: #e09f3e;
}

.list-group-item .btn-trash {
    color: #e5383b;
}

.list-group-item .fa-star {
    width: 35px;
    height: 35px;
    line-height: 35px;
    margin: 3px;
    font-size: 17px;
    cursor: pointer;
    color: #ffd700;
    transition: all 0.5s ease;
    transform: translateX(30px);
    opacity: 0;
}

.list-group-item.like .fa-star {
    opacity: 1;
    transform: translateX(10px);
}

.list-group-item.favourite .list-group-item-label,
.list-group-item.favourite .list-group-item-input {
    color: #e09f3e;
}
</style>