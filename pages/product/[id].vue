<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-50 via-purple-50 to-pink-50">
    <Header />
    
    <!-- Close/Exit Button -->
    <button 
      @click="goBack" 
      class="fixed top-24 right-6 z-50 bg-white text-gray-700 p-3 rounded-full shadow-lg hover:bg-gray-100 hover:shadow-xl transition-all border border-blue-400"
      title="Close"
    >
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
      </svg>
    </button>
    
    <!-- Loading State -->
    <div v-if="loading" class="flex justify-center items-center min-h-screen">
      <div class="text-center">
        <div class="animate-spin rounded-full h-16 w-16 border-t-4 border-b-4 border-blue-600 mx-auto mb-4"></div>
        <p class="text-gray-600">Loading product...</p>
      </div>
    </div>

    <!-- Error State -->
    <div v-else-if="error" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 text-center">
      <div class="text-red-600 text-xl mb-4">⚠️ Error loading product</div>
      <p class="text-gray-600 mb-4">{{ error }}</p>
      <button 
        @click="fetchProduct" 
        class="px-6 py-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition"
      >
        Try Again
      </button>
    </div>

    <!-- Product Details -->
    <div v-else-if="product" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 md:py-12">
      <!-- Back Button -->
      <button 
        @click="goBack" 
        class="mb-6 flex items-center text-blue-600 hover:text-blue-700 font-medium transition"
      >
        <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"/>
        </svg>
        Back to Products
      </button>

      <div class="bg-white rounded-3xl shadow-2xl overflow-hidden">
        <div class="grid md:grid-cols-2 gap-8 p-6 md:p-10">
          <!-- Product Image -->
          <div class="bg-gray-50 rounded-2xl p-8">
            <img 
              :src="product.thumbnail" 
              :alt="product.title"
              class="w-full h-96 object-contain mb-4"
            />
            <!-- Image Gallery -->
            <div v-if="product.images && product.images.length > 0" class="grid grid-cols-4 gap-2">
              <img 
                v-for="(img, index) in product.images.slice(0, 4)" 
                :key="index"
                :src="img" 
                :alt="`${product.title} ${index + 1}`"
                class="w-full h-20 object-cover rounded cursor-pointer hover:opacity-75 transition"
              />
            </div>
          </div>

          <!-- Product Info -->
          <div class="flex flex-col">
            <!-- Category & Brand -->
            <div class="flex gap-2 mb-4">
              <span class="inline-block px-4 py-2 bg-blue-100 text-blue-700 rounded-full text-sm font-semibold">
                {{ product.category }}
              </span>
              <span v-if="product.brand" class="inline-block px-4 py-2 bg-purple-100 text-purple-700 rounded-full text-sm font-semibold">
                {{ product.brand }}
              </span>
            </div>

            <!-- Title -->
            <h1 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">
              {{ product.title }}
            </h1>

            <!-- Rating -->
            <div class="flex items-center mb-6">
              <div class="flex items-center text-yellow-500 mr-3">
                <span class="text-2xl mr-2">⭐</span>
                <span class="text-xl font-bold">{{ product.rating || 0 }}</span>
              </div>
              <span class="text-gray-600">({{ product.stock || 0 }} in stock)</span>
            </div>

            <!-- Price -->
            <div class="mb-6">
              <span class="text-5xl font-bold text-blue-600">${{ product.price }}</span>
            </div>

            <!-- Description -->
            <div class="mb-8">
              <h2 class="text-xl font-semibold text-gray-900 mb-3">Description</h2>
              <p class="text-gray-700 leading-relaxed">{{ product.description }}</p>
            </div>

            <!-- Action Buttons -->
            <div class="flex flex-col sm:flex-row gap-4 mt-auto">
              <button 
                @click="addToCart"
                class="flex-1 px-8 py-4 bg-gradient-to-r from-blue-600 to-purple-600 text-white rounded-xl hover:from-blue-700 hover:to-purple-700 transition-all font-semibold text-lg shadow-lg hover:shadow-xl"
              >
                🛒 Add to Cart
              </button>
              <button 
                @click="addToWishlist"
                class="px-8 py-4 bg-white border-2 border-blue-600 text-blue-600 rounded-xl hover:bg-blue-50 transition-all font-semibold text-lg"
              >
                ❤️ Wishlist
              </button>
            </div>

            <!-- Additional Info -->
            <div class="mt-8 pt-8 border-t border-gray-200">
              <div class="grid grid-cols-2 gap-4 text-sm">
                <div class="flex items-center text-gray-600">
                  <svg class="w-5 h-5 mr-2 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
                  </svg>
                  Free Shipping
                </div>
                <div class="flex items-center text-gray-600">
                  <svg class="w-5 h-5 mr-2 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
                  </svg>
                  30 Day Returns
                </div>
                <div class="flex items-center text-gray-600">
                  <svg class="w-5 h-5 mr-2 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
                  </svg>
                  Secure Payment
                </div>
                <div class="flex items-center text-gray-600">
                  <svg class="w-5 h-5 mr-2 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
                  </svg>
                  Fast Delivery
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Related Products Section -->
      <div v-if="relatedProducts.length > 0" class="mt-16">
        <h2 class="text-3xl font-bold text-gray-900 mb-8">Related Products</h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
          <div 
            v-for="relatedProduct in relatedProducts" 
            :key="relatedProduct.id"
            class="bg-white rounded-2xl shadow-lg overflow-hidden hover:shadow-2xl transition-all duration-300 hover:-translate-y-2 cursor-pointer group"
            @click="goToProduct(relatedProduct.id)"
          >
            <div class="relative h-48 bg-gray-100 flex items-center justify-center p-4">
              <img 
                :src="relatedProduct.thumbnail" 
                :alt="relatedProduct.title"
                class="max-h-full max-w-full object-contain group-hover:scale-110 transition-transform duration-300"
              />
            </div>
            <div class="p-4">
              <h3 class="text-base font-semibold text-gray-900 mb-2 line-clamp-2 group-hover:text-blue-600 transition">
                {{ relatedProduct.title }}
              </h3>
              <div class="flex items-center justify-between">
                <span class="text-xl font-bold text-blue-600">${{ relatedProduct.price }}</span>
                <div class="flex items-center text-yellow-500 text-sm">
                  <span class="mr-1">⭐</span>
                  <span>{{ relatedProduct.rating || 0 }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <FooterSection />
  </div>
</template>

<script setup>
import { ref, computed, onMounted, watch } from 'vue'
import { useRoute, useRouter } from 'vue-router'

const route = useRoute()
const router = useRouter()

const product = ref(null)
const relatedProducts = ref([])
const loading = ref(true)
const error = ref(null)

const productId = computed(() => route.params.id)

const fetchProduct = async () => {
  try {
    loading.value = true
    error.value = null
    
    const response = await fetch(`https://dummyjson.com/products/${productId.value}`)
    
    if (!response.ok) {
      throw new Error('Product not found')
    }
    
    product.value = await response.json()
    
    // Fetch related products from same category
    if (product.value.category) {
      const categoryResponse = await fetch(`https://dummyjson.com/products/category/${encodeURIComponent(product.value.category)}`)
      const data = await categoryResponse.json()
      relatedProducts.value = (data.products || [])
        .filter(p => p.id !== product.value.id)
        .slice(0, 4)
    }
  } catch (err) {
    error.value = err.message
    console.error('Error fetching product:', err)
  } finally {
    loading.value = false
  }
}

const goBack = () => {
  router.back()
}

const goToProduct = (id) => {
  router.push(`/product/${id}`)
}

const addToCart = () => {
  alert(`${product.value.title} added to cart!`)
  // TODO: Implement cart functionality
}

const addToWishlist = () => {
  alert(`${product.value.title} added to wishlist!`)
  // TODO: Implement wishlist functionality
}

// Watch for route changes (when clicking related products)
watch(productId, () => {
  fetchProduct()
}, { immediate: false })

onMounted(() => {
  fetchProduct()
})
</script>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
