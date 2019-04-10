<template>
  <div class='row'>
  </div>
</template>

<script>
import { EventBus } from '../../EventBus.js'
import Cell from './Cell.vue'


export default {
  name: 'Row',
  props: {
    grid: String,
    rowNum: Number
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .row {
      border: 1px solid black;
      background-color: lightyellow;
      display: grid;
      grid-template-columns: repeat(auto-fit, 1fr);;
      grid-template-rows: 1fr;
    }
</style>
