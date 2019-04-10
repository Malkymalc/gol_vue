<template>
  <div id='grid'>
    Grid
  </div>
</template>

<script>
import { EventBus } from '../../EventBus.js'

export default {
  name: 'Grid',
  props: {
    msg: String
  },
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
    }
</style>
