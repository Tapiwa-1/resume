<template>
  <div class="md:grid md:grid-cols-3 gap-8 max-w-4xl mx-auto text-justify">
        <!-- Approachable -->
        <div v-for="text in texts" :key="text.id" class=" text-justify mb-10 md:mb-0">
          <h2 class="text-lg md:text-lg font-bold text-gray-800 mb-6">{{ text.heading }}</h2>
          <p class="text-md md:text-md text-gray-600">
            {{ text.description }}
        </p>
        </div>
      </div>
</template>

<script setup>
defineProps({
    texts: Array
})
</script>

