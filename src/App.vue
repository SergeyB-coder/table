<template>
  <div>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <TableMain/> -->
    <!-- <ListReadyDelivers/> -->
    <!-- <GenerateTizer/> -->
    <!-- <TizersDeliver/>
    <NewDeliver/> -->
    <SettingsFids/>
  </div>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

// import TableMain from './components/TableMain.vue'
// import AddUser from './components/AddUser.vue'
// import AddSource from './components/AddSource.vue'
// import MainPage from './components/main/MainPage.vue'
// import ListDelivers from './components/delivers/ListDelivers.vue'
// import StopDeliver from './components/StopDeliver.vue'
// import ImportDelivers from './components/delivers/ImportDelivers.vue'
// import NewDeliver from './components/newdeliver/NewDeliver.vue'
// import TizersDeliver from './components/newdeliver/TizersDeliver.vue'
// import GenerateTizer from './components/newdeliver/GenerateTizer.vue'
// import ListReadyDelivers from './components/newdeliver/ListReadyDelivers.vue';

import SettingsFids from './components/settings/SettingsFids'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // TableMain,
    // AddUser
    // AddSource
    // ListDelivers
    // StopDeliver
    // MainPage
    // NewDeliver
    // TizersDeliver
    // GenerateTizer
    // ListReadyDelivers
    SettingsFids
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
