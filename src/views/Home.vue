<template>
  <div>
    <h1>
        Welcome to Rapid Food
    </h1>
  </div>
</template>

<script setup>
import { computed, onMounted, ref } from 'vue';
import store from '../store';
import axiosClient from '../axiosClient.js'
import YouTubeButton from '../components/YouTubeButton.vue';
// import Meals from '../components/Meals.vue';

const random = ref([])

onMounted(async () => {
    const response = await axiosClient.get('random.php')
    console.log(response.data)
    random.value = response.data
})

</script>