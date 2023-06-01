<template>
    <a 
        :href="href" 
        target="_blank" 
        class="px-3 py-2 font-semibold rounded border border-red-600 bg-red-300 hover:bg-red-600 hover:text-white transition-colors"
    >
        <slot>YouTube</slot>
    </a>
</template>

<script setup>
const props = defineProps({
    href: String
})

</script>