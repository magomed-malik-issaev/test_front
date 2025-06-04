<script setup lang="ts">
import { ref } from 'vue'

const searchQuery = ref('')
const activeTab = ref('Affiliés')

const sidebarSections = [
  { label: 'A-E', count: 7, key: 'ae' },
  { label: 'F-J', count: 5, key: 'fj' },
  { label: 'K-O', count: 3, key: 'ko' },
  { label: 'P-T', count: 8, key: 'pt' },
  { label: 'U-Z', count: 4, key: 'uz' }
]

const tabs = ['Affiliés', 'Parcours', 'Suivi']
</script>

<template>
  <div class="min-h-screen bg-gray-50 flex">
    <!-- Sidebar - 304px selon spécifications -->
    <div class="bg-white border-r border-gray-200 flex flex-col" style="width: 304px;">
      <!-- Logo -->
      <div class="p-6 border-b border-gray-200">
        <h1 class="text-2xl font-medium text-blue-600 flex items-center">
          <span class="text-3xl mr-2">⚡</span>
          <span class="text-blue-700">Easybrief</span>
        </h1>
      </div>

      <!-- Search Bar -->
      <div class="p-6">
        <div class="relative">
          <svg class="absolute left-4 top-1/2 transform -translate-y-1/2 h-4 w-4 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
          </svg>
          <input
            v-model="searchQuery"
            type="text"
            placeholder="Rechercher"
            class="w-full pl-12 pr-4 py-3 text-sm border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent bg-gray-50"
          />
        </div>
      </div>

      <!-- Tabs -->
      <div class="border-b border-gray-200">
        <nav class="flex">
          <button
            v-for="tab in tabs"
            :key="tab"
            @click="activeTab = tab"
            :class="[
              'flex-1 py-4 px-6 text-sm font-medium text-center border-b-4 transition-colors',
              activeTab === tab
                ? 'border-blue-500 text-blue-600'
                : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300'
            ]"
          >
            {{ tab }}
          </button>
        </nav>
      </div>

      <!-- Sidebar Content -->
      <div class="flex-1 p-6">
        <div class="space-y-1">
          <div
            v-for="section in sidebarSections"
            :key="section.key"
            class="flex items-center justify-between py-4 px-3 hover:bg-gray-50 rounded-lg cursor-pointer group"
          >
            <div class="flex flex-col">
              <span class="font-semibold text-gray-900 text-lg">{{ section.label }}</span>
              <span class="text-sm text-blue-600">{{ section.count }} personnes</span>
            </div>
            <svg class="h-5 w-5 text-black" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
            </svg>
          </div>
        </div>
      </div>
    </div>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col">
      <!-- Main Area -->
      <div class="flex-1 p-8 flex items-center justify-center">
        <div class="max-w-lg w-full">
          <!-- Dashed Border Container -->
          <div class="border-2 border-dashed border-blue-300 rounded-lg p-12 text-center bg-white">
            <div class="space-y-6">
              <div>
                <h2 class="text-3xl font-light text-blue-500 mb-2">
                  Commencez un suivi
                </h2>
                <h3 class="text-3xl font-light text-blue-600">
                  avec l'affilié de votre choix.
                </h3>
              </div>
              
              <p class="text-gray-600 text-lg">
                Lancer un suivi avec l'un de vos affiliés du jour.
              </p>
              
              <div class="pt-4">
                <button class="inline-flex items-center px-6 py-3 bg-blue-600 text-white font-medium rounded-md hover:bg-blue-700 transition-colors">
                  <svg class="mr-2 h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                  </svg>
                  Sélectionner un affilié
                  <svg class="ml-2 h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                  </svg>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Styles personnalisés si nécessaire */
</style>
