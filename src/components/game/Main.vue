<template>
  <main id="main">
    <button id='start_pause' v-on:click="playPauseClicked">Start / Pause</button>
    <button id='reset' v-on:click="resetClicked">Reset</button>
    <Grid :grid='grid'/>
  </main>
</template>

<script>
import { EventBus } from '../../EventBus.js'
import Grid from '../grid/Grid.vue'

export default {
  name: 'Main',
  props: {
    grid: Array
  },
  components: {
    Grid,
  },
  methods: {
    playPauseClicked(){
      EventBus.$emit('play-pause', null);
    },
    resetClicked(){
      EventBus.$emit('reset-grid', null);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #main {
    background-color: lightgreen;
    height: 85vh;
    width: 100vw;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
  }
  #start_pause, #reset, #grid {
    border: 1px solid black;
    width: 50vmax;
    margin: 0 auto;
  }
  #grid {
    height: 50vmax;
  }
  #start_pause, #reset {
    height: 10vmax;
  }
</style>
