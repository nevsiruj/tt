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
          v-for="profile in profiles"
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
};
const categoryTitle = categoryTitles[category] || "Categoría no encontrada";

// Datos hardcodeados para perfiles
const profiles = [
  {
    id: 1,
    name: "Jessica",
    description: "Una morocha encantadora con mucha energía.",
    phone: "5493512337746",
    image: "https://via.placeholder.com/300x200?text=Jessica",
  },
  {
    id: 2,
    name: "Salome",
    description: "Momentos únicos con masajes descontracturantes.",
    phone: "5493512483317",
    image: "https://via.placeholder.com/300x200?text=Salome",
  },
  {
    id: 3,
    name: "Fiamma",
    description: "Profesional y real, placer garantizado.",
    phone: "5493515731825",
    image: "https://via.placeholder.com/300x200?text=Fiamma",
  },
  {
    id: 4,
    name: "Florencia",
    description: "Experiencia especial para disfrutar al máximo.",
    phone: "5493517611007",
    image: "https://via.placeholder.com/300x200?text=Florencia",
  },
  {
    id: 5,
    name: "Alegra",
    description: "Sensual, divertida, y siempre dispuesta.",
    phone: "5493516370539",
    image: "https://via.placeholder.com/300x200?text=Alegra",
  },
  {
    id: 6,
    name: "Eli Trans",
    description: "Últimos días en Córdoba, no te lo pierdas.",
    phone: "5493513124078",
    image: "https://via.placeholder.com/300x200?text=Eli+Trans",
  },
];
</script>

<style>
/* Agrega personalizaciones si las necesitas */
</style>
