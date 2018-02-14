<template>
  <div class="container">
    <div class="app-wrapper">
      <div class="search-and-total">
        <app-search @search="changeSearchVal"></app-search>
        <app-total :data="filteredTable"></app-total>
      </div>
         <app-table :data="filteredTable"></app-table> 
    </div>
  </div>
</template>

<script>

import Search from './components/Search.vue';
import Table from './components/Table.vue';
import Total from './components/Total';
import data from './data/test.json';

export default {
  name: 'app',
  data () {
    return {
      data : data,
      search : ''
    }
  },
  computed : {
filteredTable() {
      if (!this.search) {
        return this.data;
      }
      return this.data.filter((item) => {
        return Object.values(item).reduce((acc, el) => {
          if (el.toString().toLowerCase().match(this.search.toLowerCase())) {
            return true;
          }
          return acc;
        }, false);
      })
  }
  },
  methods : {
    changeSearchVal(value) {
      this.search = value;
    }
  },
  components  : {
    appSearch : Search,
    appTable : Table,
    appTotal : Total
  }
}
</script>

<style>

  body {
    padding-top: 40px;
    padding-bottom: 30px;
    background: grey;
  }

  .app-wrapper {
    width: 850px;
    margin: 0 auto;
    background: white;
    border-radius: 5px;
  }

</style>
