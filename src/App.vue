<template>
  <div id="app">
    <div class="row">
      <Header :varFromParent="var01" @newList="updateList($event)" />
    </div>
    <div class="row">
      <TableHeadings />
    </div>
    <div class="row">
      <DataTable
        :varFromParent="var01"
        @newList="updateList($event)"
        style="position: relative; width: 100%"
      />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import TableHeadings from './components/TableHeadings.vue';
import DataTable from './components/DataTable.vue';

export default {
  name: 'App',
  components: {
    Header,
    TableHeadings,
    DataTable,
  },
  methods: {
    updateList(varFromChild) {
      this.var01 = varFromChild.data;
    },
  },
  data: () => ({
    var01: [
      ['title01', 'description01', '2022-11-03', 'med', false],
      ['title02', 'description02', '2022-11-03', 'med', true],
    ],
  }),
};
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
button {
  width: 100px;
}
</style>
