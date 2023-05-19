<template>
  <div>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <TableMain/> -->
    <ListDelivers/>
  </div>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

// import TableMain from './components/TableMain.vue'
// import AddUser from './components/AddUser.vue'
// import AddSource from './components/AddSource.vue'
// import MainPage from './components/main/MainPage.vue'
import ListDelivers from './components/delivers/ListDelivers.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // TableMain,
    // AddUser
    // AddSource
    ListDelivers
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
