<template>
  <div>
    <!-- Hero Section -->
    <section
      class="bg-cover bg-center h-96 relative"
      style="background-image: url('/hero-image.jpg')"
    >
      <div
        class="absolute inset-0 bg-black bg-opacity-50 flex items-center justify-center"
      >
        <div class="text-center text-white">
          <h2 class="text-5xl font-bold mb-4">
            Bienvenido a Traslasierra Tentaciones
          </h2>
          <p class="text-lg mb-6">
            Donde la exclusividad se encuentra con tus deseos más profundos.
          </p>
          <button
            class="bg-red-600 hover:bg-red-700 text-white py-2 px-6 rounded text-lg"
          >
            Explorar Ahora
          </button>
        </div>
      </div>
    </section>

    <!-- Categorías -->
    <CategoriesList />

    <!-- Beneficios -->
    <section class="py-12 bg-gray-900 text-white">
      <div class="container mx-auto text-center">
        <h2 class="text-3xl font-bold mb-6">
          ¿Por qué elegir Traslasierra Tentaciones?
        </h2>
        <ul class="space-y-4 text-lg">
          <li>🌟 Privacidad absoluta en cada conexión.</li>
          <li>🔥 Acompañantes para todos los gustos y preferencias.</li>
          <li>
            🔎 Buscador avanzado para encontrar lo que deseas rápidamente.
          </li>
          <li>💬 Contacto directo sin intermediarios.</li>
        </ul>
      </div>
    </section>
  </div>
</template>
