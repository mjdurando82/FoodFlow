<template>
  <div class="meals">
    <h5 class="meal-list-title">Meal List</h5>
    <div class="add-meal-container">
      <input v-on:input="handleChange" type="text" :value="mealInput" placeholder="Add a Meal" class="add-meal-input">
      <button class="add-meal-btn" type="submit" @click="addMeal">Add</button>
    </div>
    <ul class="meal-list">
      <li v-for="(meal, index) in meals" :key="index" class="meal-item">
        <span class="meal-name">{{ meal }}</span>
        <button class="remove-meal" @click="removeMeal(index)">&#9747;</button>
      </li>
    </ul>
    <section class="clear-all-container">
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
input {
  border-radius: 1rem;
}
.meal-list-title {
  color: #000000;
  margin-bottom: 1rem;
  text-align: center;
}

.add-meal-container {
  display: flex;
  margin-bottom: 1rem;
  width: 30vw;
}

.add-meal-input {
  flex: 1;
  padding: 0.5rem;
  border: none;
  border-bottom: 1px solid #000;
  font-size: 16px;
  background-color: #fff;
  color: #000;
}

.add-meal-btn {
  margin-left: 1rem;
  background-color: #2f833c94;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 10rem;
}

.add-meal-btn:hover {
  background-color: #139f50;
}

.meal-list {
  margin-top: 1rem;
}

.meal-item {
  display: flex;
  align-items: center;
  margin-bottom: 0.5rem;
}

.meal-name {
  margin-left: 1rem;
  flex: 1;
  color: black;
  padding-top: 0.2rem;
  font-family:monospace;
}

.remove-meal {
  margin-left: 1rem;
  color: red;
  cursor: pointer;
}

.remove-meal:hover {
  color: #ff0000;
}

.clear-all-container {
  display: flex;
  justify-content: center;
  margin-top: 1rem;
}

.clear-all-btn {
  background-color: #dc3546c1;
  color: #fff;
  border-radius: 10rem;
  padding: 0.5rem 1rem;
  cursor: pointer;
}

.clear-all-btn:hover {
  background-color: #b41a2a;
}

.meals {
background-image: url(https://i.pinimg.com/originals/6f/a6/61/6fa6616ba2cdc63d1f4f34ae06006bd0.png);
  background-size: cover;
  border-radius: 2rem;
  padding: 1rem;
  background-color: #f9f9f9;
}
</style>
