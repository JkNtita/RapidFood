<template>
    <h3 class="text-gray-600 mb-4 mt-20 text-center">Search for Meals using Letters below!</h3>
    <div class="mt-2 flex justify-center gap-2">
            <!-- <pre>{{ letters }}</pre> -->
        <router-link 
        :to="{name: 'byLetter', params: {letter} }" 
        v-for="letter of letters" 
        :key="letter"
    >
        <!-- <router-link v-for="(letter, index) of letters" :to="`/meals/${index}`" :key="index"> -->
            {{ letter }}
        </router-link>
    </div>
    <Meals :meals="meals" />
</template>

<script setup>
import { computed } from '@vue/reactivity';
import { useRoute } from 'vue-router';
import { onMounted, watch } from 'vue';
import store from '../store';
import Meals from '../components/Meals.vue';


const route = useRoute();
const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split("");
const meals = computed(() => store.state.mealsByLetter)

watch(() => {
    store.dispatch('searchMealsByLetter', route.params.letter)    
})

onMounted(() => {
    store.dispatch('searchMealsByLetter', route.params.letter)
})

</script>