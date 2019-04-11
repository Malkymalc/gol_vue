<template>
  <button class='cell'>
  </button>
</template>

<script>
import { EventBus } from '../../EventBus.js'


export default {
  name: 'Cell',
  props: {
    cellNum: Number,
    rowNum: Number
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .cell {
      border: 0.1px solid black;
      border-radius: 50%;
      background-color: green;
    }
</style>
