<template>
    <div>
        <button @click="asyncIncrement({by: 50, duration: 500})">+</button>
        <button @click="asyncDecrement({by: 50, duration: 500})">-</button>
    </div>
</template>

<script>
import { mapActions } from 'vuex'

    export default {
        methods: {
            ...mapActions([ 
                'asyncIncrement',
                'asyncDecrement'
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