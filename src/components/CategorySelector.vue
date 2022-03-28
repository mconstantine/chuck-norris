<template>
  <select v-model="currentCategory" @change="onCurrentCategoryChange">
    <option :value="defaultCategory" selected>Any category</option>
    <option v-for="category in categories" :key="category" :value="category">
      {{ category }}
    </option>
  </select>
</template>

<script>
  export const DEFAULT_CATEGORY = "Any"

  export default {
    name: 'CategorySelector',
    props: {
      categories: Array
    },
    data() {
      return {
        defaultCategory: DEFAULT_CATEGORY,
        currentCategory: DEFAULT_CATEGORY
      }
    },
    methods: {
      onCurrentCategoryChange() {
        this.$emit('categoryChange', this.currentCategory)
      }
    },
  }
</script>

<style lang="sass">

  select
    padding: 1em 2em

</style>
