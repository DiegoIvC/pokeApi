<script setup>

</script>

<template>
  <nav class="bg-blue-500 p-4">
    <div class="container mx-auto flex justify-between items-center">
      <div class="text-white text-xl font-bold">
        <router-link to="/">MiApp</router-link>
      </div>
      <ul class="flex space-x-4">
        <li>
          <router-link to="/" class="text-white hover:text-gray-200">Home</router-link>
        </li>
        <li>
          <router-link to="/about" class="text-white hover:text-gray-200">About</router-link>
        </li>
        <li>
          <router-link to="/contact" class="text-white hover:text-gray-200">Contact</router-link>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>

</style>