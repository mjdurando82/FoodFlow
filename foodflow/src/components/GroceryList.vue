<template>
  <div class="groceries">
    <h5 class="grocery-list-title">Grocery List</h5>
    <div class="add-item-container">
      <input v-on:input="handleChange" type="text" :value="ItemInput" placeholder="Add a Grocery Item" class="add-item-input">
      <button class="add-item-btn" type="submit" @click="addItem">Add</button>
    </div>
    <ul class="grocery-list">
      <li class="grocery-item" v-for="(item, index) in items" :key="index" :class="{ 'checked': item.checked }">
        <input type="checkbox" v-model="item.checked" class="checkbox">
        <span class="item-name">{{ item.name }}</span>
        <button class="remove-item" @click="removeItem(index)">&#9747;</button>
      </li>
    </ul>
    <section class="clear-all-container">
      <button class="clear-all-btn" @click="clearAll">Clear All</button>
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
    handleChange(e) {
      this.ItemInput = e.target.value
    },
    addItem() {
      if (this.ItemInput !== '') {
        this.items.push({ name: this.ItemInput, checked: false })
        this.ItemInput = ''
      }
    }, 
    removeItem(index) {
      this.items.splice(index, 1)
    }, 
    clearAll() {
      this.items = []
    }
  }
}
</script>

<style>
li {
  list-style: none;
}
input {
  border-radius: 1rem;
}
.grocery-list-title {
  color: #fff;
  margin-bottom: 1rem;
  text-align: center;
}
.add-item-container {
  display: flex;
  margin-bottom: 1rem;
}
.add-item-input {
  flex: 1;
  padding: 0.5rem;
  border: none;
  border-bottom: 1px solid #000;
  font-size: 16px;
  background-color: #fff;
  color: #000;
}
.add-item-btn {
  margin-left: 1rem;
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 10rem;
}
.add-item-btn:hover {
  background-color: #1c62ad;
}
.grocery-list {
  margin-top: 1rem;
}
.grocery-item {
  display: flex;
  align-items: center;
  margin-bottom: 0.5rem;
}
.item-name {
  margin-left: 1rem;
  flex: 1;
  color: #fff;
}
.checkbox {
  margin-right: 1rem;
}
.remove-item {
  margin-left: 1rem;
  color: red;
  cursor: pointer;
}
.checked {
  text-decoration: line-through;
}
.clear-all-container {
  display: flex;
  justify-content: center;
  margin-top: 1rem;
}
.clear-all-btn {
  background-color: #dc3545;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 10rem;
}
.clear-all-btn:hover {
  background-color: #b41a2a;
}
.groceries {
  background-color: rgba(255, 68, 0, 0.645);
  border: solid 2px rgba(255, 255, 0, 0.622);
  border-radius: 2rem;
  padding: 1rem;
}
</style>
