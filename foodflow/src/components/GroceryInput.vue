<template>
  <div>
    <label>Groceries: </label>
    <input v-on:input="handleChange" type="text" placeholder="Add a Grocery Item">
    <button>Add Item</button>
  </div>

</template>

<script>
export default {
  name: 'GroceryInput'
}
</script>


<style>
</style>