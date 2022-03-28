<template>
  <div>
    <nav>
      <CategorySelector
        :categories="categories"
        @categoryChange="$emit('categoryChange', $event)"
      />
    </nav>

  </div>
</template>

<script>
  import CategorySelector from './CategorySelector.vue'
  import axios from 'axios'

  export default {
    name: 'HeaderSearch',

    components: {
      CategorySelector,
    },

    data() {
      return {
        categories: [],
        joke: null
      }
    },

    mounted() {
      axios.get('https://api.chucknorris.io/jokes/categories').then(response => {
        this.categories = response.data;
      })
    },
  }
</script>

<style lang="sass" scoped>
  @import '../assets/style/_variables.sass'

  nav
    width: 100%

    padding: 2em 2em
    border-bottom: solid 1px #333

    text-align: right



</style>
