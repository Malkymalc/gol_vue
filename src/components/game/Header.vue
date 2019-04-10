<template>
  <header id="header">
    <h1>Header</h1>
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
    height: 15vh;
    width: 100vw;
    margin: 0;
    padding: 0;
  }
</style>
