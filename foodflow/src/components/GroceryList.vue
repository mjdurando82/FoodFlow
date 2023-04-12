<template>
  <div>
    <h2>Food Flow</h2>
    <h5>Grocery List</h5>
    <input v-on:input="handleChange" type="text" :value="ItemInput" placeholder="Add a Grocery Item">
    <button class="add" type="submit" @click="addItem">Add</button>
    <ul>
      <li v-for="item, index in items" :key="index">
        {{ item }}
        <button class="remove" type="button" @click="removeItem(index)">
<span>&#10003;</span></button>
      </li>
    </ul>
    <section>
      <button @click="clearAll"> Clear All</button>
    </section>
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
    }, 
    clearAll(){
      this.items = []
    }
  }
}
</script>


<style>
li {
  list-style: none;
}
.add {
  margin-left: 1vw;
}
.remove {
  margin-left: 1vw;
}
</style>