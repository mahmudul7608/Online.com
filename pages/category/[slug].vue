<template>
  <div class="min-h-screen bg-white">
    <Header />
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
      <h1 class="text-4xl font-bold text-gray-900 mb-4 capitalize">{{ categoryName }} Category</h1>
      <p class="text-gray-600 mb-12">Browse products in this category</p>
      
      <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-6">
        <div class="bg-gray-50 p-8 rounded-lg text-center">
          <p class="text-gray-600">Products coming soon...</p>
        </div>
      </div>
    </div>

    <FooterSection />
  </div>
</template>

<script setup>
import { computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const categoryName = computed(() => {
  const slug = route.params.slug
  return slug ? slug.toString().replace(/-/g, ' ') : 'Category'
})
</script>
