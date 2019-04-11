<template>
  <div id="game">
    <Header />
    <Main :gridArray='gridArray'/>
  </div>
</template>


<script>
import { EventBus } from '../EventBus.js'
import life from '../models/gameOfLife.js'
import Header from './game/Header.vue'
import Main from './game/Main.vue'

export default {
  name: 'Game',
  components: {
    Header,
    Main
  },
  data(){
    return {
      gridArray: life.getBlankGrid(),
      play: false,
    }
  },
  created(){
    EventBus.$on('play-pause', () => {
      const isPlaying = this.play;
      this.play = isPlaying ? false : true;
      console.log(this.play);
    });

    EventBus.$on('reset-grid', () => {
      this.gridArray = life.getBlankGrid();
    });

    EventBus.$on('cell-clicked', coords => {
      const newArray = [...this.gridArray]
      const { row, cell } = coords;
      const alive = newArray[row][cell];
      newArray[row][cell] = alive ? false : true;
      this.gridArray = newArray;
      console.log(this.gridArray[row][cell]);
    });

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #game {
    background-color: lightpink;
    height: 100vh;
    width: 100vw;
    margin: 0;
    padding: 0;
  }
</style>
