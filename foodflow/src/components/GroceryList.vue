<template>
  <div>
    <label>Groceries: </label>
    <input v-on:input="handleChange" type="text" :value="ItemInput" placeholder="Add a Grocery Item">
    <button type="submit" @click="addItem">Add Item</button>
    <ul>
      <li v-for="item, index in items" :key="index">
        {{ item }}
        <button type="button" @click="removeItem(index)">X</button>
      </li>
    </ul>
  </div>

</template>

<script>
export default {
  name: 'GroceryList',
  data: () => ({ 
    ItemInput: '',
    items: []

  }),
  methods: {
    handleChange(e){
      this.ItemInput = e.target.value
    },
    addItem(){
      this.items.push(this.ItemInput)
      this.ItemInput = ''
    }, 
    removeItem(index){
      this.items.splice(index, 1)
    }
  }
}
</script>


<style>
</style>