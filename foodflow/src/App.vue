<template>
  <div class="container">
    <header>
      <div class="banner">
        <img src="https://t3.ftcdn.net/jpg/03/86/58/88/240_F_386588859_BH4uUobRxT4ZFG8SS1qGYUxmDmRVqcpr.jpg" alt="Logo" />
      </div>
    </header>
    <div class="content">
      <h2>Food Flow</h2>
      <div class="list-container">
        <GroceryList />
        <MealList />
      </div>
    </div>
  </div>
</template>

<script>
import GroceryList from './components/GroceryList.vue';
import MealList from './components/MealList.vue';

export default {
  name: 'App',
  components: {
    GroceryList,
    MealList
  }
}
</script>

<style>
body {
  background-color: #f6fef0;
  margin: 0;
  padding: 0;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem;
}

header {
  height: 5rem;
}

.banner {
  width: 100vw;
  height: 20vh;
  overflow: hidden;
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1;
}

.banner img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transform: rotateX(180deg);
}

h2 {
  font-family: 'Calligraffitti', cursive;
  font-weight: 700;
  font-size: 3rem;
  text-shadow: -15px 5px 20px #ced3cf;
  letter-spacing: 0.02em;
  text-align: center;
  color: #2f833c94;
  margin-bottom: 4rem;
}

.list-container {
  display: flex;
  justify-content: space-evenly;
}
</style>
