<template>
    <div class="m-4">
        <h1>Counter: {{ counter }}</h1>
        <div class="d-flex gap-2">
            <button @click="onIncrement" class="btn btn-outline-success">Add</button>
            <button @click="onDecrement" class="btn btn-outline-danger">Delete</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            counter: 0,
        }

    },
    methods: {
        onIncrement() {
            this.counter += 1
        },
        onDecrement() {
            this.counter -= 1
        },
    }
}
</script>

<style></style>