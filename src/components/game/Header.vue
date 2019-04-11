<template>
  <header id="header">
      <button>Options</button>
    <h1>
      <small>Conway's</small>
      <br>
      <span>Game of Life</span>
    </h1>
    <button>?</button>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #header {
    background-color: lightblue;
    font-size: 0.8rem;
    height: 12vh;
    width: 100vw;
    margin: 0;
    padding: 0;
    display: grid;
    grid-template-columns: 1fr 3fr 1fr;
    /* justify-content: space-around;
    align-items: center; */
    text-align: center;
  }
</style>
