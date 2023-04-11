<template>
  <div id="app">  
    <img alt="Vue logo" src="./assets/logo.png">
    <GroceryInput />
    <GroceryList />
  </div>
</template>

<script>
import GroceryList from './components/GroceryList.vue'
import GroceryInput from './components/GroceryInput.vue'

export default {
  name: 'App',
  components: {
    GroceryList,
    GroceryInput
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
