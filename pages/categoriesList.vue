<template>
  <div class="py-12 bg-gray-50">
    <div class="container mx-auto">
      <h2 class="text-3xl font-bold text-center mb-8">
        Explora Nuestras Categorías
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <NuxtLink
          v-for="category in categories"
          :key="category.id"
          :to="`/categories/${category.id}`"
          class="bg-white shadow-lg rounded-lg p-6 text-center hover:bg-gray-100 transition"
        >
          <div class="mb-4">
            <img
              :src="category.image"
              :alt="category.name"
              class="w-24 h-24 mx-auto rounded-full object-cover"
            />
          </div>
          <h3 class="text-xl font-bold mb-2">{{ category.name }}</h3>
          <p class="text-gray-700">{{ category.description }}</p>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
const categories = [
  {
    id: 'women',
    name: 'Mujeres',
    description: 'Compañeras exclusivas y únicas.',
    image: '/images/women.jpg',
  },
  {
    id: 'men',
    name: 'Hombres',
    description: 'Conéctate con los mejores acompañantes masculinos.',
    image: '/images/men.jpg',
  },
  {
    id: 'trans',
    name: 'Trans',
    description: 'Experiencias auténticas y personalizadas.',
    image: '/images/trans.jpg',
  },
];
</script>

<style scoped>
/* Si necesitas estilos adicionales */
</style>
