<script setup>
</script>

<template>
  <nav class="bg-blue-500 p-4">
    <div class="container mx-auto flex justify-between items-center">
      <div class="text-white text-xl font-bold">
        <router-link to="/">Pokemons</router-link>
      </div>
      <ul class="flex space-x-4">
        <li>
          <router-link to="/" class="text-white hover:text-gray-200">Limpiar pagina</router-link>
        </li>
      </ul>
    </div>
  </nav>
  <router-view></router-view>
</template>

<style scoped>
</style>
