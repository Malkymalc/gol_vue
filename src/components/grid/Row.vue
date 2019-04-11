<template>
  <div v-bind:id="(rowNum + 1).toString().padStart(6, 'row-0')" class="row">
    <button
      v-for="(cell, i) in row"
      v-bind:id="rowNum.toString().concat(i.toString())"
      class="Cell"
      v-bind:rowNum="rowNum"
      v-bind:cellNum="i"
      v-on:click="cellClicked(rowNum, i)"
    />
  </div>
</template>

<script>
import { EventBus } from '../../EventBus.js'
import Cell from './Cell.vue'


export default {
  name: 'Row',
  props: {
    row: Array,
    rowNum: Number
  },
  components: {
    Cell
  },
  methods: {
    cellClicked(rowNum, i){
      EventBus.$emit('cell-clicked', {row: rowNum, cell: i});
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .row {
      border: 1px solid black;
      background-color: lightyellow;
      display: grid;
      grid-template-rows: 1fr;
      grid-template-columns: repeat(auto-fit, 0.95vmax);
}
</style>
