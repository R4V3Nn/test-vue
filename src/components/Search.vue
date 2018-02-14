<template>
  <div class="search-wrapper">
      <h3>Search</h3>
      <input type="text" class="input is-primary is-medium" v-model="value" @keyup="searchInput">
  </div>
</template>

<script>
export default {
    data() {
        return {
            value : ''
        }
    },
    methods : {
        searchInput() {
            this.$emit('search', this.value);
        }
    }
}
</script>

<style>

    h3 {
        font-size: 22px;
        text-align: center;
    }

    .search-wrapper {
        max-width: 800px;
        margin: 0 auto;
        padding-top: 20px;
        margin-bottom: 30px;

    }
</style>


