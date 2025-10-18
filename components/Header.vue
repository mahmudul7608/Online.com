<template>
  <nav class="border-b border-gray-200 relative bg-white shadow-sm">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <NuxtLink to="/" class="flex items-center group">
          <span class="text-2xl font-bold">
            <span class="text-blue-600">Online</span><span class="text-orange-500">.Com</span>
          </span>
        </NuxtLink>

        <!-- Desktop Navigation Links -->
        <ul class="hidden md:flex items-center space-x-6 lg:space-x-8">
          <li><NuxtLink to="/search" class="text-blue-600 hover:text-blue-700 transition-colors font-medium text-sm lg:text-base">Search</NuxtLink></li>
          <li><NuxtLink to="/about" class="text-blue-600 hover:text-blue-700 transition-colors font-medium text-sm lg:text-base">About</NuxtLink></li>
          <li><NuxtLink to="/contact" class="text-blue-600 hover:text-blue-700 transition-colors font-medium text-sm lg:text-base">Contact</NuxtLink></li>
          <li><NuxtLink to="/wishlist" class="text-blue-600 hover:text-blue-700 transition-colors font-medium text-sm lg:text-base">Wish list</NuxtLink></li>
          <li><NuxtLink to="/signin" class="text-blue-600 hover:text-blue-700 transition-colors font-medium text-sm lg:text-base">signin</NuxtLink></li>
          <li><NuxtLink to="/signup" class="text-blue-600 hover:text-blue-700 transition-colors font-medium text-sm lg:text-base">SignUp</NuxtLink></li>
        </ul>

        <!-- Mobile Menu Button -->
        <button @click="toggleMenu" class="md:hidden text-blue-600 focus:outline-none hover:text-blue-700 transition-colors">
          <svg v-if="!isMenuOpen" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
          <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div v-if="isMenuOpen" class="md:hidden bg-white border-t border-gray-200">
      <ul class="px-4 py-4 space-y-3">
        <li><NuxtLink @click="toggleMenu" to="/search" class="block text-blue-600 hover:text-blue-700 transition-colors font-medium py-2">Search</NuxtLink></li>
        <li><NuxtLink @click="toggleMenu" to="/about" class="block text-blue-600 hover:text-blue-700 transition-colors font-medium py-2">About</NuxtLink></li>
        <li><NuxtLink @click="toggleMenu" to="/contact" class="block text-blue-600 hover:text-blue-700 transition-colors font-medium py-2">Contact</NuxtLink></li>
        <li><NuxtLink @click="toggleMenu" to="/wishlist" class="block text-blue-600 hover:text-blue-700 transition-colors font-medium py-2">Wish list</NuxtLink></li>
        <li><NuxtLink @click="toggleMenu" to="/signin" class="block text-blue-600 hover:text-blue-700 transition-colors font-medium py-2">signin</NuxtLink></li>
        <li><NuxtLink @click="toggleMenu" to="/signup" class="block text-blue-600 hover:text-blue-700 transition-colors font-medium py-2">SignUp</NuxtLink></li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>
