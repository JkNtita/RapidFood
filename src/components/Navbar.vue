<template>
    <header
      class="bg-dark text-white shadow h-16 justify-end flex items-stretch mx-0 @apply opacity-100 translate-y-0 shadow-[0_10px_30px_0_rgb(33,33,33,0.15)] transition-all duration-[0.3s] ease-[ease-out] px-0 py-2.5;
      -webkit-transition: all 0.3s ease-out fixed-top mb-40
    ">
      <router-link
      :to="{name: 'home'}" class="inline-flex mx-0 items-center px-2 h-full font-semibold hover:bg-gray-300 hover:font-semibold hover:bg-white hover:text-black transition-colors">
        Home
      </router-link>
      <div class="flex items-center gap-1 mx-0">
        <router-link :to="{name: 'byName'}" class="inline-flex mx-0 items-center px-2 h-full font-semibold hover:bg-gray-400 hover:font-semibold hover:bg-white hover:text-black transition-colors">
          Search Meals
        </router-link>
      </div>
      <div>
        <router-link :to="{name: 'byLetter'}" class="inline-flex mx-0 items-center px-2 h-full font-semibold hover:bg-gray-400 hover:font-semibold hover:bg-white hover:text-black transition-colors">
          Meals by letter
        </router-link >
      </div>
      <div>
        <router-link :to="{name: 'ingredients'}" class="inline-flex mx-0 items-center px-2 h-full font-semibold hover:bg-gray-400 hover:font-semibold hover:bg-white hover:text-black transition-colors">
          Meals by Ingredients
        </router-link>
      </div>
    </header>
</template>