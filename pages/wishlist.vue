<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-50 via-purple-50 to-pink-50">
    <Header />
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 md:py-12">
      <h1 class="text-3xl md:text-4xl font-bold text-gray-900 mb-8">My Wishlist</h1>
      
      <div class="text-center py-20">
        <div class="text-gray-400 text-6xl mb-4">❤️</div>
        <h2 class="text-2xl font-semibold text-gray-700 mb-2">Your wishlist is empty</h2>
        <p class="text-gray-600 mb-6">Start adding products to your wishlist</p>
        <NuxtLink to="/search" class="inline-block px-6 py-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition">
          Browse Products
        </NuxtLink>
      </div>
    </div>
    
    <FooterSection />
  </div>
</template>

<script setup>
// Wishlist page
</script>
