<template>
  <div class="meals">
    <h5>Meal List</h5>
    <div class="add-meal-container">
      <input v-on:input="handleChange" type="text" :value="mealInput" placeholder="Add a Meal" class="add-item-input">
      <button class="add-item-btn" type="submit" @click="addMeal">Add</button>
    </div>
    <ul class="meal-list">
      <li v-for="(meal, index) in meals" :key="index" >
        <span class="meal-name">{{ meal }}</span>
        <button class="remove-meal" @click="removeMeal(index)">&#9747;</button>
      </li>
    </ul>
    <section>
      <button class="clear-all-btn" @click="clearAll">Clear All</button>
    </section>
  </div>
</template>

<script>
export default {
  name: 'MealList',
  data: () => ({ 
    mealInput: '',
    meals: []
  }),
  methods: {
    handleChange(e) {
      this.mealInput = e.target.value
    },
    addMeal() {
      if (this.mealInput !== '') {
        this.meals.push(this.mealInput)
        this.mealInput = ''
      }
    }, 
    removeMeal(index) {
      this.meals.splice(index, 1)
    }, 
    clearAll() {
      this.meals = []
    }
  }
}
</script>

<style>
li {
  list-style: none;
}
.add-meal-container {
  display: flex;
  margin-bottom: 1rem;
}
.add-meal-input {
  flex: 1;
  padding: 0.5rem;
  border: none;
  border-bottom: 1px solid #000;
  font-size: 16px;
}
.add-meal-btn {
  margin-left: 1rem;
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
}
.add-meal-btn:hover {
  background-color: #1c62ad;
}
.meal-list {
  margin-top: 1rem;
}
.meal-name {
  margin-left: 1rem;
  flex: 1;
}
.checkbox {
  margin-right: 1rem;
}
.remove-meal {
  margin-left: 1rem;
  color: red;
  cursor: pointer;
}
.checked {
  text-decoration: line-through;
}
.clear-all-btn {
  background-color: #dc3545;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
}
.clear-all-btn:hover {
  background-color: #b41a2a;
}
.meals {
  background-color: rgb(29, 143, 73);
  border: solid 2px #283398;
  border-radius: 2rem;
  padding: 1rem;
}
</style>
