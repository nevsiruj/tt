<template>
  <footer class="p-6 bg-gray-800 text-white mt-auto">
    <div class="container mx-auto flex flex-col md:flex-row justify-between items-center space-y-4 md:space-y-0">
      <!-- Información de la Plataforma -->
      <div class="text-center md:text-left">
        <h2 class="text-xl font-bold">Tentaciones Traslasierra</h2>
        <p class="text-sm text-gray-400">
          Conecta, descubre y disfruta con personas exclusivas. Privacidad y profesionalismo garantizados.
        </p>
        <p class="text-xs text-gray-500 mt-2">
          &copy; {{ new Date().getFullYear() }} Tentaciones Traslasierra. Todos los derechos reservados.
        </p>
      </div>

      <!-- Enlace a Redes Sociales -->
      <div class="flex space-x-6 items-center">
        <!-- Telegram -->
        <a
          href="https://t.me/tu_canal_o_grupo"
          target="_blank"
          rel="noopener noreferrer"
          class="hover:opacity-80 transition"
        >
          <img
            src="https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg"
            alt="Telegram Logo"
            class="w-8 h-8 telegram-logo"
          />
        </a>
      </div>
    </div>
  </footer>
</template>

<script setup>
// No es necesario añadir lógica adicional aquí
</script>

<style scoped>
footer {
  font-family: Arial, sans-serif;
}

/* Ajustes para el logo de Telegram */
.telegram-logo {
  filter: brightness(1) invert(5); /* Cambia a blanco para fondos oscuros */
}

.telegram-logo:hover {
  filter: none; /* Restaura los colores originales al pasar el mouse */
}
</style>
