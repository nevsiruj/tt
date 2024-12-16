<template>
  <div class="min-h-screen bg-gray-100">
    <!-- Header -->
    <header class="bg-black text-white py-6">
      <div class="container mx-auto">
        <h1 class="text-4xl font-bold">{{ category.name }}</h1>
        <p class="text-lg mt-2">{{ category.description }}</p>
      </div>
    </header>

    <!-- Perfiles -->
    <section class="py-12">
      <div class="container mx-auto">
        <h2 class="text-3xl font-bold text-center mb-8">
          Descubre nuestros perfiles
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div
            v-for="profile in category.profiles"
            :key="profile.id"
            class="bg-white shadow-lg rounded-lg p-6 text-center"
          >
            <div class="mb-4">
              <img
                :src="profile.image"
                :alt="profile.name"
                class="w-24 h-24 mx-auto rounded-full object-cover"
              />
            </div>
            <h3 class="text-xl font-bold mb-2">{{ profile.name }}</h3>
            <p class="text-gray-700">{{ profile.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { useRoute } from 'vue-router';

// Datos hardcodeados
const categories = {
  women: {
    name: 'Mujeres',
    description: 'Compañeras exclusivas para cada momento especial.',
    profiles: [
      {
        id: 1,
        name: 'María',
        description: 'Sofisticada y encantadora.',
        image: '/images/profile1.jpg',
      },
      {
        id: 2,
        name: 'Lucía',
        description: 'Atractiva y elegante.',
        image: '/images/profile2.jpg',
      },
      {
        id: 3,
        name: 'Carla',
        description: 'Amigable y apasionada.',
        image: '/images/profile3.jpg',
      },
    ],
  },
  men: {
    name: 'Hombres',
    description: 'Acompañantes masculinos de clase mundial.',
    profiles: [
      {
        id: 1,
        name: 'Carlos',
        description: 'Caballero encantador.',
        image: '/images/profile4.jpg',
      },
      {
        id: 2,
        name: 'Julián',
        description: 'Divertido y sofisticado.',
        image: '/images/profile5.jpg',
      },
      {
        id: 3,
        name: 'David',
        description: 'Apasionado y carismático.',
        image: '/images/profile6.jpg',
      },
    ],
  },
  trans: {
    name: 'Trans',
    description: 'Experiencias únicas y personalizadas.',
    profiles: [
      {
        id: 1,
        name: 'Sofía',
        description: 'Auténtica y empática.',
        image: '/images/profile7.jpg',
      },
      {
        id: 2,
        name: 'Valentina',
        description: 'Carismática y elegante.',
        image: '/images/profile8.jpg',
      },
      {
        id: 3,
        name: 'Camila',
        description: 'Enérgica y amigable.',
        image: '/images/profile9.jpg',
      },
    ],
  },
};

// Ruta actual
const route = useRoute();
const category = categories[route.params.category] || {
  name: 'Categoría no encontrada',
  description: '',
  profiles: [],
};
</script>
