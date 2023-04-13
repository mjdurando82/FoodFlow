<template>
  <div class="groceries">
    <h5 class="grocery-list-title">Grocery List</h5>
    <div class="add-item-container">
      <input v-on:input="handleChange" type="text" :value="ItemInput" placeholder="Add a Grocery Item" class="add-item-input">
      <button class="add-item-btn" type="submit" @click="addItem">Add</button>
    </div>
<ul class="grocery-list">
  <li class="grocery-item" v-for="(item, index) in items" :key="index">
    <input type="checkbox" v-model="item.checked" class="checkbox">
    <span class="item-name" :class="{ 'checked': item.checked }">{{ item.name }}</span>
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
  color: #000000;
  margin-bottom: 1rem;
  text-align: center;
}
.add-item-container {
  display: flex;
  margin-bottom: 1rem;
  width: 30vw;
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
  background-color: #2f833c94;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 10rem;
}
.add-item-btn:hover {
  background-color: #139f50;
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
  color: black;
  padding-top: 0.1rem;
  font-family:monospace;

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
  color: green;
}

.groceries {
  background-image: url(https://i.pinimg.com/originals/6f/a6/61/6fa6616ba2cdc63d1f4f34ae06006bd0.png);
  background-size: cover;
  border-radius: 2rem;
  padding: 1rem;
  background-color: #f9f9f9;
}
</style>
