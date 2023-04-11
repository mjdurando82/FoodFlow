<template>
  <div class="list">
  </div>
</template>

<script>
export default {
  name: 'GroceryList',
  data: () => ({
    items: [], 
    ItemInput: ''
  }), 
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
