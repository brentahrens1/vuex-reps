<template>
  <div id="app">
    <h1>Vuex</h1>
    <app-result></app-result>
    <app-counter></app-counter>
    <app-another-result></app-another-result>
    <app-another-counter></app-another-counter>
    <hr>
    <input type="text" v-model="value">
    <p>{{ value }}</p>
  </div>
</template>

<script>
import Result from './components/Result'
import Counter from './components/Counter'
import AnotherResult from './components/AnotherResult'
import AnotherCounter from './components/AnotherCounter'

export default {
  computed: {
    value: {
      get() {
        return this.$store.getters.value
      },
      set(value) {
        this.$store.dispatch('updateValue', value)
      }
    }
  },
  methods: {
    updateValue(event) {
      this.$store.dispatch('updateValue', event.target.value)
    }
  },
  components: {
    appResult: Result,
    appCounter: Counter,
    appAnotherResult: AnotherResult,
    appAnotherCounter: AnotherCounter
  }
}
</script>

<style>
  hr {
    width: calc(100vw - 5rem);
    color: #aaaaaa;
  }

  input {
    width: 10rem;
    padding: .5rem;
    border-radius: 5px;
    outline: none;
    border: 1px solid #000;
    font-size: 1rem;
  }
</style>
