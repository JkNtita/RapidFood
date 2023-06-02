<template>
  <div class="banner-container">
    <div class="banner-image"></div>
    <h1 class="banner-text">
      Welcome to Rapid Food
    </h1>
    <h2 class="lead banner-lead">We aim to help you create fancy food descriptions in less time than it would take the average restaurant to serve you drinks.</h2>
    <div v-if="random.length > 0" class="random-meals">
      <h3>Random Meals:</h3>
      <ul>
        <li v-for="meal in random" :key="meal.idMeal">{{ meal.strMeal }}</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.banner-container {
  position: relative;
  height: 100vh;
  width: 100%;
}

.banner-image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("../assets/banner.jpg");
  background-size: cover;
  filter: blur(20%);
}

.banner-text,
.banner-lead {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  color: rgb(27, 27, 27);
}

.banner-text {
  font-size: 3rem;
  margin-top: 100px;

}

.banner-lead {
  font-size: 1.5rem;
  margin-top: 200px;
}

.random-meals {
  margin-top: 40px;
}

.random-meals h3 {
  font-size: 1.5rem;
}

.random-meals ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.random-meals li {
  margin-bottom: 8px;
}
</style>

<script setup>
import { onMounted, ref } from 'vue';
import axiosClient from '../axiosClient.js';

const random = ref([]);

onMounted(async () => {
  const response = await axiosClient.get('random.php');
  random.value = response.data.meals || [];
});
</script>
