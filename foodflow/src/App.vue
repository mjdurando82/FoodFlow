<template>
  <div id="app">  
    <GroceryList handleChange="handleChange"/>
    <MealList />
  </div>
</template>

<script>
import GroceryList from './components/GroceryList.vue'
import MealList from './components/MealList.vue'

export default {
  name: 'App',
  components: {
    GroceryList,
    MealList
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
</style>
