<template>
  <section class="py-16 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-4xl font-bold text-center text-gray-900 mb-12">FEATURED PRODUCTS</h2>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        <NuxtLink 
          v-for="product in featuredProducts" 
          :key="product.id"
          :to="`/product/${product.id}`"
          class="bg-white rounded-lg shadow-md hover:shadow-xl transition overflow-hidden transform hover:scale-105"
        >
          <img :src="product.image" :alt="product.name" class="w-full h-48 object-cover" />
          <div class="p-6">
            <h4 class="text-xl font-bold text-purple-600 mb-2">{{ product.price }}</h4>
            <p class="text-gray-700 mb-4 line-clamp-2">{{ product.name }}</p>
            <p class="text-sm text-gray-500 flex items-center mb-2">
              <i class="fa-solid fa-clipboard-list mr-2"></i>{{ product.store }}
            </p>
            <p class="text-sm text-gray-500 flex items-center">
              <i class="fa-sharp fa-solid fa-list mr-2"></i>{{ product.category }}
            </p>
          </div>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
const featuredProducts = [
  {
    id: 1,
    name: 'Canon EOS 90D camera body with EF-S 18-135mm',
    price: '140,000 TK',
    image: 'https://www.cloud.ryanscomputers.com/cdn/products/small/canon-eos-90d-camera-body-with-ef-s-18-135mm-11574775657.webp',
    store: 'Ryans',
    category: 'Camera & Accessories'
  },
  {
    id: 2,
    name: 'Canon EOS 90D camera body with EF-S 18-135mm',
    price: '140,000 TK',
    image: 'https://www.cloud.ryanscomputers.com/cdn/products/small/canon-eos-90d-camera-body-with-ef-s-18-135mm-11574775657.webp',
    store: 'Ryans',
    category: 'Camera & Accessories'
  },
  {
    id: 3,
    name: 'VISION 75" LED 3D 4K H01 Smart',
    price: '160,000 TK',
    image: 'https://images.othoba.com/images/thumbs/0363665_vision-75-led-tv-3d-4k-h01-smart_300.jpeg',
    store: 'Othoba',
    category: 'Home Appliances'
  },
  {
    id: 4,
    name: 'VISION 75" LED 3D 4K H01 Smart',
    price: '160,000 TK',
    image: 'https://images.othoba.com/images/thumbs/0363665_vision-75-led-tv-3d-4k-h01-smart_300.jpeg',
    store: 'Othoba',
    category: 'Home Appliances'
  },
  {
    id: 5,
    name: 'TVS Apache RTR 160 4v Blue Double Disc',
    price: '223,999 TK',
    image: 'https://images.othoba.com/images/thumbs/0136679_tvs-apache-rtr-160-4v-blue-double-disc_300.jpeg',
    store: 'Othoba',
    category: 'Bikes & Cars'
  },
  {
    id: 6,
    name: 'TVS Apache RTR 160 4v Blue Double Disc',
    price: '223,999 TK',
    image: 'https://images.othoba.com/images/thumbs/0136679_tvs-apache-rtr-160-4v-blue-double-disc_300.jpeg',
    store: 'Othoba',
    category: 'Bikes & Cars'
  },
  {
    id: 7,
    name: 'Apple MacBook Pro (Late 2021) Apple M1 Max 16"',
    price: '360,000 TK',
    image: 'https://www.cloud.ryanscomputers.com/cdn/products/small/apple-macbook-pro-late-2021-apple-m1-max-162-11636265644.webp',
    store: 'Ryans',
    category: 'Computer, Laptops & Accessories'
  },
  {
    id: 8,
    name: 'Apple MacBook Pro (Late 2021) Apple M1 Max 16"',
    price: '360,000 TK',
    image: 'https://www.cloud.ryanscomputers.com/cdn/products/small/apple-macbook-pro-late-2021-apple-m1-max-162-11636265644.webp',
    store: 'Ryans',
    category: 'Computer, Laptops & Accessories'
  }
]
</script>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
