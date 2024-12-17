<template>
  <div class="bg-gray-100 min-h-screen py-8">
    <!-- Header -->
    <header class="bg-blue-600 text-white py-4">
      <div class="container mx-auto text-center">
        <h1 class="text-4xl font-bold">{{ categoryTitle }}</h1>
        <p class="text-lg mt-2">Descubre las mejores opciones para ti</p>
      </div>
    </header>

    <!-- Grid de Perfiles -->
    <section class="container mx-auto py-8 px-4">
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
        <!-- Cada perfil redirige a su página individual -->
        <NuxtLink
          v-for="profile in filteredProfiles"
          :key="profile.id"
          :to="`/profiles/${profile.id}`"
          class="bg-white rounded-lg shadow-lg overflow-hidden hover:shadow-2xl transition transform hover:-translate-y-1"
        >
          <!-- Imagen -->
          <img
            :src="profile.image"
            :alt="profile.name"
            class="w-full h-48 object-cover"
          />

          <!-- Detalles del perfil -->
          <div class="p-4 text-center">
            <h2 class="text-xl font-bold mb-2">{{ profile.name }}</h2>
            <p class="text-gray-700 text-sm mb-2">{{ profile.description }}</p>
            <span class="inline-block bg-blue-500 text-white py-2 px-4 rounded">
              Ver Perfil
            </span>
          </div>
        </NuxtLink>
      </div>
    </section>
  </div>
</template>

<script setup>
import { useRoute } from "vue-router";

// Obtener parámetros de la ruta
const route = useRoute();
const category = route.params.category;

// Títulos dinámicos
const categoryTitles = {
  women: "Acompañantes Mujeres",
  men: "Acompañantes Hombres",
  trans: "Acompañantes Trans",
  maduras: "Acompañantes Maduras",
  masajes: "Masajistas Especializadas",
};
const categoryTitle = categoryTitles[category] || "Categoría no encontrada";

// Datos hardcodeados para perfiles
const profiles = [
  // Categoría Women
  {
    id: 1,
    category: "women",
    name: "Jessica",
    description: "Una morocha encantadora con mucha energía.",
    image: "https://via.placeholder.com/300x200?text=Jessica",
  },
  {
    id: 2,
    category: "women",
    name: "Salome",
    description: "Momentos únicos con masajes descontracturantes.",
    image: "https://via.placeholder.com/300x200?text=Salome",
  },

  // Categoría Men
  {
    id: 3,
    category: "men",
    name: "Carlos",
    description: "Un caballero sofisticado y encantador.",
    image: "https://via.placeholder.com/300x200?text=Carlos",
  },
  {
    id: 4,
    category: "men",
    name: "Julián",
    description: "Divertido, elegante y apasionado.",
    image: "https://via.placeholder.com/300x200?text=Julian",
  },

  // Categoría Trans
  {
    id: 5,
    category: "trans",
    name: "Eli Trans",
    description: "Últimos días en Córdoba, no te lo pierdas.",
    image: "https://via.placeholder.com/300x200?text=Eli+Trans",
  },
  {
    id: 6,
    category: "trans",
    name: "Sofía",
    description: "Auténtica y empática, te encantará.",
    image: "https://via.placeholder.com/300x200?text=Sofia",
  },

  // Categoría Maduras
  {
    id: 7,
    category: "maduras",
    name: "Laura",
    description: "Madura y experimentada, una experiencia única.",
    image: "https://via.placeholder.com/300x200?text=Laura",
  },
  {
    id: 8,
    category: "maduras",
    name: "Carla",
    description: "Elegancia y clase en cada encuentro.",
    image: "https://via.placeholder.com/300x200?text=Carla",
  },

  // Categoría Masajes
  {
    id: 9,
    category: "masajes",
    name: "Luna",
    description: "Masajes relajantes y descontracturantes.",
    image: "https://via.placeholder.com/300x200?text=Luna",
  },
  {
    id: 10,
    category: "masajes",
    name: "Paz",
    description: "Experta en masajes tantricos y lingam.",
    image: "https://via.placeholder.com/300x200?text=Paz",
  },
];

// Filtrar perfiles según la categoría seleccionada
const filteredProfiles = profiles.filter((profile) => profile.category === category);
</script>

<style scoped>
/* Agrega personalizaciones si las necesitas */
</style>
