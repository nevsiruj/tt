<template>
    <div class="bg-gray-100 min-h-screen py-8">
      <div class="container mx-auto px-4">
        <h1 class="text-3xl font-bold mb-4">{{ profile.name }}</h1>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <!-- Imagen -->
          <img
            :src="profile.image"
            :alt="profile.name"
            class="rounded-lg shadow-lg object-cover"
          />
  
          <!-- Detalles -->
          <div>
            <p><strong>Descripción:</strong> {{ profile.description }}</p>
            <p><strong>Teléfono:</strong> {{ profile.phone }}</p>
            <a
              :href="`https://wa.me/${profile.phone}`"
              target="_blank"
              class="mt-4 inline-block bg-green-500 text-white py-2 px-4 rounded hover:bg-green-600"
            >
              Contactar por WhatsApp
            </a>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { useRoute } from "vue-router";
  
  const route = useRoute();
  const profileId = parseInt(route.params.id);
  
  // Datos de ejemplo
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
  ];
  
  // Encuentra el perfil específico
  const profile = profiles.find((p) => p.id === profileId);
  </script>
  