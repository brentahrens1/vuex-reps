<template>
    <div>
        <button @click="increment(100)">+</button>
        <button @click="decrement(50)">-</button>
    </div>
</template>

<script>
import { mapActions } from 'vuex'
    export default {
        methods: {
            ...mapActions([
                'increment',
                'decrement'
            ])
        }
    }

</script>

<style scoped>
    button {
        background: lightblue;
        width: 10rem;
        border-radius: 5px;
        color: #fff;
        padding: .5rem;
        outline: none;
        margin-left: .5rem;
        font-size: 1.2rem;
    }
</style>