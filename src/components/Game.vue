<template>
  <div id="game">
    <Header />
    <Main />
  </div>
</template>


<script>
import { EventBus } from '../EventBus.js'
import Header from './game/Header.vue'
import Main from './game/Main.vue'


const playPause = () => {
  console.log('playPause method firing');
}
const resetGrid = () => {
  console.log('resetGrid method firing');
}


EventBus.$on('play-pause', playPause);
EventBus.$on('reset-grid', resetGrid);


export default {
  name: 'Game',
  components: {
    Header,
    Main
  },
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
