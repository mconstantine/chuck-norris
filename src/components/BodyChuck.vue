<template>
  <div>
    <h2 v-if="joke">
      {{joke.value}}
    </h2>
  </div>
</template>

<script>
  export default {
    name: 'BodyChuck',

    props: {
      joke: Object
    },

    data() {
      return {

      }
    },

  }
</script>

<style scoped lang="sass">
  div
    padding-top: 3em
</style>
