<template>
  <div class="bg-gray-900 text-white min-h-screen flex flex-col justify-center items-center">
    <!-- Advertencia de Edad -->
    <section v-if="!accepted" class="fixed inset-0 flex flex-col items-center justify-center bg-black bg-opacity-90 text-center p-6">
      <div class="bg-gray-800 p-8 rounded-lg shadow-lg max-w-lg">
        <img src="" alt="Tentaciones Traslasierra" class="w-48 mx-auto mb-4" />
        <h1 class="text-3xl font-bold mb-4">Bienvenido a Tentaciones Traslasierra</h1>
        <p class="mb-6">
          Esta plataforma está destinada únicamente para personas mayores de 18 años. Si eres menor, por favor **SAL** de esta página.
        </p>
        <div class="space-x-4">
          <button
            @click="acceptConditions"
            class="bg-green-500 hover:bg-green-600 text-white py-2 px-6 rounded transition"
          >
            Ingresar
          </button>
          <button
            @click="exitPage"
            class="bg-red-500 hover:bg-red-600 text-white py-2 px-6 rounded transition"
          >
            Salir
          </button>
        </div>
      </div>
    </section>

    <!-- Contenido Principal -->
    <div v-else class="container mx-auto py-12 px-6">
      <!-- Encabezado -->
      <header class="text-center mb-12">
        <img src="" alt="Tentaciones Traslasierra" class="w-48 mx-auto mb-4" />
        <h1 class="text-4xl font-bold">Tentaciones Traslasierra</h1>
        <p class="text-lg mt-4">
          La mejor plataforma online para descubrir, conectar y disfrutar con personas exclusivas. Eventos, encuentros, contenido digital y mucho más.
        </p>
      </header>

      <!-- Categorías -->
      <section class="mb-12">
        <h2 class="text-3xl font-bold mb-6 text-center">Elegí tu Categoría</h2>
        <div class="grid grid-cols-2 md:grid-cols-5 gap-6">
          <NuxtLink
            v-for="category in categories"
            :key="category.id"
            :to="category.link"
            class="bg-white text-gray-800 p-4 rounded-lg shadow-lg text-center hover:bg-gray-200 transition"
          >
            <img :src="category.image" :alt="category.name" class="w-32 h-32 mx-auto object-cover rounded-full mb-2" />
            <h3 class="text-lg font-bold">{{ category.name }}</h3>
          </NuxtLink>
        </div>
      </section>

      <!-- Beneficios -->
      <section class="bg-gray-800 p-6 rounded-lg shadow-lg text-center">
        <h2 class="text-2xl font-bold mb-4">¿Por qué elegir Tentaciones Traslasierra?</h2>
        <ul class="space-y-3">
          <li>🌟 Privacidad y anonimato garantizados.</li>
          <li>🔥 Encuentra acompañantes para todos los gustos.</li>
          <li>💬 Contacto directo sin intermediarios.</li>
          <li>🔎 Buscador avanzado para tu comodidad.</li>
          <li>📸 Contenido exclusivo y personalizado.</li>
        </ul>
      </section>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const accepted = ref(false);

const acceptConditions = () => {
  accepted.value = true;
};

const exitPage = () => {
  window.location.href = "https://www.google.com"; // Redirige a otra página
};

// Categorías Hardcodeadas
const categories = [
  { id: 1, name: "Mujeres", link: "/categories/women", image: "https://via.placeholder.com/150x150?text=Mujeres" },
  { id: 2, name: "Maduras", link: "/categories/maduras", image: "https://via.placeholder.com/150x150?text=Maduras" },
  { id: 3, name: "Masajes", link: "/categories/masajes", image: "https://via.placeholder.com/150x150?text=Masajes" },
  { id: 4, name: "Hombres", link: "/categories/men", image: "https://via.placeholder.com/150x150?text=Hombres" },
  { id: 5, name: "Trans", link: "/categories/trans", image: "https://via.placeholder.com/150x150?text=Trans" },
];
</script>

<style>
/* Estilo adicional si es necesario */
</style>
