<template>
  <div id="app">  
    <GroceryList handleChange="handleChange"/>
  </div>
</template>

<script>
import GroceryList from './components/GroceryList.vue'

export default {
  name: 'App',
  components: {
    GroceryList
  },
  methods: {
    addItem(){
      let itemList = [...this.items, this.ItemInput]
      this.items = itemList
      this.ItemInput = ''
    }, 
    handleChange(e){
      this.ItemInput = e.target.value
    }
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
