<template>
  <section class="py-16 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-4xl font-bold text-center text-gray-900 mb-12">BROWSE TOP CATEGORIES</h2>
      
      <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-6">
        <NuxtLink 
          v-for="category in categories" 
          :key="category.name"
          :to="`/category/${category.slug}`"
          class="flex flex-col items-center p-6 bg-gray-50 rounded-lg hover:shadow-lg hover:bg-purple-50 transition cursor-pointer transform hover:scale-105"
        >
          <img :src="category.icon" :alt="category.name" class="w-16 h-16 mb-4" />
          <p class="text-sm text-center text-gray-700">{{ category.name }}</p>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
const categories = [
  { name: 'Book', icon: 'https://mullokoto.com/category-icon/book.svg', slug: 'book' },
  { name: 'Mobile, Tablet & Accessories', icon: 'https://mullokoto.com/category-icon/smartphone.svg', slug: 'mobile-tablet' },
  { name: 'Computer, Laptop & Accessories', icon: 'https://mullokoto.com/category-icon/laptop.svg', slug: 'computer-laptop' },
  { name: 'Software', icon: 'https://mullokoto.com/category-icon/software.svg', slug: 'software' },
  { name: 'Fashion & Beauty', icon: 'https://mullokoto.com/category-icon/fashion.svg', slug: 'fashion-beauty' },
  { name: 'Gaming', icon: 'https://mullokoto.com/category-icon/gaming.svg', slug: 'gaming' },
  { name: 'Home Application', icon: 'https://mullokoto.com/category-icon/applience.svg', slug: 'home-application' },
  { name: 'Home Electrical & Electronics', icon: 'https://mullokoto.com/category-icon/home-appliance.svg', slug: 'home-electrical' },
  { name: 'Construction & Tools', icon: 'https://mullokoto.com/category-icon/construction.svg', slug: 'construction-tools' },
  { name: 'Baby & Toys', icon: 'https://mullokoto.com/category-icon/baby.svg', slug: 'baby-toys' },
  { name: 'Kitchen & Dining', icon: 'https://mullokoto.com/category-icon/kitchen.svg', slug: 'kitchen-dining' },
  { name: 'Food & Groceries', icon: 'https://mullokoto.com/category-icon/food.svg', slug: 'food-groceries' },
  { name: 'Sports & Fitness', icon: 'https://mullokoto.com/category-icon/sport.svg', slug: 'sports-fitness' },
  { name: 'Security', icon: 'https://mullokoto.com/category-icon/security.svg', slug: 'security' },
  { name: 'Bike & Cars', icon: 'https://mullokoto.com/category-icon/bike.svg', slug: 'bike-cars' },
  { name: 'Camera & Accessories', icon: 'https://mullokoto.com/category-icon/camera.svg', slug: 'camera' },
  { name: 'Gadgets & Stationary', icon: 'https://mullokoto.com/category-icon/gadget.svg', slug: 'gadgets' },
  { name: 'Cooking Materials', icon: 'https://mullokoto.com/category-icon/cooking.svg', slug: 'cooking' },
  { name: 'Gift', icon: 'https://mullokoto.com/category-icon/gift.svg', slug: 'gift' },
  { name: 'Travel & Accessories', icon: 'https://mullokoto.com/category-icon/travel.svg', slug: 'travel' },
  { name: 'Office', icon: 'https://mullokoto.com/category-icon/office.svg', slug: 'office' },
  { name: 'Pets', icon: 'https://mullokoto.com/category-icon/pet.svg', slug: 'pets' },
  { name: 'Health', icon: 'https://mullokoto.com/category-icon/first-aid-kit.svg', slug: 'health' },
  { name: 'Service', icon: 'https://mullokoto.com/category-icon/service.svg', slug: 'service' }
]
</script>
