<template>
  <div id="app">
    <h2>Food Flow</h2>
    <div class="list-container">
      <GroceryList handleChange="handleChange"/>
      <MealList />
    </div>
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
  }
}
</script>

<style>
.list-container {
  display: flex;
  justify-content: space-evenly;
}
</style>
