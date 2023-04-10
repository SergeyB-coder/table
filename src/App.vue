<template>
  <div>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <TableMain/>
  </div>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import TableMain from './components/TableMain.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    TableMain
  }
}
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
