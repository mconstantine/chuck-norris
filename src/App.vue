<template>
  <div id="app">
    <HeaderSearch @categoryChange="onCurrentCategoryChange" />
    <BodyChuck :joke="joke" />
  </div>
</template>

<script>
  import HeaderSearch from './components/HeaderSearch.vue';
  import BodyChuck from './components/BodyChuck.vue';
  import axios from 'axios'

  export default {
    name: 'App',

    components: {
      HeaderSearch,
      BodyChuck,
    },

    data() {
      return {
        joke: null
      }
    },

    methods: {
      onCurrentCategoryChange(currentCategory) {
        axios
          .get(`https://api.chucknorris.io/jokes/random?category=${currentCategory}`)
          .then(response => {
            this.joke = response.data
          })
      }
    }
  }
</script>

<style lang="sass">
@import './assets/style/_variables.sass'

#app
  font-family: Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50
</style>
