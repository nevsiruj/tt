<template>
  <header class="p-4 bg-gray-800 text-white flex flex-col md:flex-row md:items-center md:justify-between space-y-4 md:space-y-0">
    <!-- Navegación -->
    <nav class="flex items-center space-x-6">
      <NuxtLink to="/" class="hover:text-purple-400">🏠 Home</NuxtLink>
      <NuxtLink to="/anunciar" class="hover:text-purple-400">ℹ️ Anunciar</NuxtLink>
    </nav>

    <!-- Servicios -->
    <div class="flex items-center justify-center space-x-4">
      <div class="text-center">
        <span>👥</span>
        <p class="text-xs">Encuentros</p>
      </div>
      <div class="text-center">
        <span>📹</span>
        <p class="text-xs">Videollamadas</p>
      </div>
      <div class="text-center">
        <span>🎥</span>
        <p class="text-xs">Venta Videos</p>
      </div>
      <div class="text-center">
        <span>🖼️</span>
        <p class="text-xs">Venta Fotos</p>
      </div>
    </div>

    <!-- Buscador Rápido -->
    <div class="flex flex-col sm:flex-row items-center space-y-4 sm:space-y-0 sm:space-x-4">
      <!-- Buscar por Usuario -->
      <input
        type="text"
        v-model="searchQuery"
        placeholder="Buscar por usuario..."
        class="p-2 w-full sm:w-auto rounded bg-gray-700 text-white placeholder-gray-400 focus:outline-none focus:ring focus:ring-purple-500"
      />

      <!-- Selección de Zonas -->
      <select
        v-model="selectedZone"
        class="p-2 w-full sm:w-auto rounded bg-gray-700 text-white focus:outline-none focus:ring focus:ring-purple-500"
      >
        <option value="" disabled selected>Seleccionar zona...</option>
        <option v-for="zone in zones" :key="zone" :value="zone">
          {{ zone }}
        </option>
      </select>

      <!-- Botón de Búsqueda -->
      <button
        @click="search"
        class="bg-purple-500 hover:bg-purple-600 text-white py-2 px-4 rounded transition"
      >
        🔍 Buscar
      </button>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const searchQuery = ref(''); // Búsqueda por usuario
const selectedZone = ref(''); // Búsqueda por zona
const router = useRouter();

// Lista de zonas ordenada alfabéticamente
const zones = [
  'Arroyo de los Patos',
  'La Paz',
  'Las Rosas',
  'Las Tapias',
  'Los Cerrillos',
  'Los Molles',
  'Merlo',
  'Mina Clavero',
  'Nono',
  'San Javier & Yacanto',
  'San José',
  'San Pedro',
  'San Vicente',
  'Travesia',
  'Villa Dolores',
  'Villa Sarmiento',
].sort(); // Ordena alfabéticamente

// Función de búsqueda
const search = () => {
  if (searchQuery.value.trim()) {
    // Si hay un usuario buscado, redirige al perfil
    router.push(`/profiles/${searchQuery.value.trim().toLowerCase()}`);
  } else if (selectedZone.value) {
    // Si hay una zona seleccionada, redirige a la lista filtrada por zona
    router.push(`/zones/${selectedZone.value.toLowerCase().replace(/\s+/g, '-')}`);
  }
};
</script>

<style scoped>
/* Ajustes para mantener el diseño limpio */
header {
  font-family: Arial, sans-serif;
}

/* Ajusta la separación entre los elementos en pantallas pequeñas */
@media (max-width: 768px) {
  header {
    flex-direction: column;
  }
}
</style>
