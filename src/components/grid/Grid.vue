<template>
  <div id='grid'>
    <Row
      v-for="(row, i) in grid"
      v-bind:rowNum="i"
    />
  </div>
</template>

<script>
import { EventBus } from '../../EventBus.js'
import Row from './Row.vue'


export default {
  name: 'Grid',
  props: {
    grid: Array
  },
  components: {
    Row,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #grid {
      border: 1px solid black;
      width: 50vmax;
      margin: 0 auto;
      height: 50vmax;
      background-color: lightpink;
      display: grid;
      grid-template-columns: 1fr;
      grid-template-rows: repeat(auto-fit, 1fr);
    }
</style>
