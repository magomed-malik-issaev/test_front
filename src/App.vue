<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="min-h-screen bg-gray-100 py-8">
    <div class="max-w-4xl mx-auto text-center">
      <div class="flex justify-center items-center space-x-8 mb-8">
        <a href="https://vite.dev" target="_blank" class="transition-transform hover:scale-110">
          <img src="/vite.svg" class="h-24 w-24" alt="Vite logo" />
        </a>
        <a href="https://vuejs.org/" target="_blank" class="transition-transform hover:scale-110">
          <img src="./assets/vue.svg" class="h-24 w-24" alt="Vue logo" />
        </a>
      </div>
      
      <div class="bg-white rounded-lg shadow-lg p-8">
        <h1 class="text-4xl font-bold text-gray-800 mb-4">Tailwind CSS Installé !</h1>
        <p class="text-lg text-gray-600 mb-6">
          Votre projet Vue.js utilise maintenant la dernière version de Tailwind CSS.
        </p>
        <div class="flex flex-wrap justify-center gap-4">
          <span class="px-4 py-2 bg-blue-500 text-white rounded-full">Vue.js</span>
          <span class="px-4 py-2 bg-green-500 text-white rounded-full">Vite</span>
          <span class="px-4 py-2 bg-purple-500 text-white rounded-full">Tailwind CSS</span>
        </div>
      </div>
      
      <HelloWorld msg="Vite + Vue + Tailwind CSS" />
    </div>
  </div>
</template>

<style scoped>
/* Styles personnalisés si nécessaire */
</style>
