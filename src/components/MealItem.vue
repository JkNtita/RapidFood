<template>
    <div 
        class="bg-white shadow rounded-xl"
    >
        <router-link :to="{name: 'mealDetails', params: {id: meal.idMeal}}">
            <img 
                :src="meal.strMealThumb" 
                :alt="meal.strMeal" 
                class="rounded-t-xl w-full h-48 object-cover" 
            />
        </router-link>
        <div class="p-3">
            <h3 class="font-bold">{{ meal.strMeal }}</h3>
            <p class="mb-4">
                Lorem ipsum dolor sit amet. 33 sapiente voluptatem et laboriosam iusto in sint maxime 
                est consequatur internos et doloremque quaerat aut exercitationem quidem.
            </p>
            <div class="flex items-center justify-between">
                <YouTubeButton :href="meal.strYoutube"></YouTubeButton>
                    <!-- <router-link 
                        class="px-3 py-2 font-semibold rounded border border-green-600 bg-green-300 hover:bg-green-600 hover:text-white transition-colors" 
                        to="/">
                            View
                    </router-link> -->
            </div>
        </div>
    </div>
</template>

<script setup>
import YouTubeButton from './YouTubeButton.vue';


const { meal } = defineProps({
    meal: {
        required: true,
        type: Object
    }
})
</script>