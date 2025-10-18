<template>
  <footer class="bg-gray-900 text-white py-12">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid md:grid-cols-4 gap-8">
        <div class="md:col-span-1">
          <h1 class="text-3xl font-bold text-stone-100 pb-3">Online.Com</h1>
          <p class="text-gray-400">
            Online.com compares the prices of your desired products from all of
            the major e-commerce in Bangladesh and helps you find the best
            deals.
          </p>
        </div>

        <div>
          <h3 class="text-xl font-bold mb-4">Important Links</h3>
          <ul class="space-y-2">
            <li>
              <NuxtLink
                to="/about"
                class="text-gray-400 hover:text-white transition"
                >About Us</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/contact"
                class="text-gray-400 hover:text-white transition"
                >Contact Us</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/privacy"
                class="text-gray-400 hover:text-white transition"
                >Privacy Policy</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/partner"
                class="text-gray-400 hover:text-white transition"
                >Become partner</NuxtLink
              >
            </li>
          </ul>
        </div>

        <div>
          <h3 class="text-xl font-bold mb-4">Top Category</h3>
          <ul class="space-y-2">
            <li>
              <NuxtLink
                to="/category/book"
                class="text-gray-400 hover:text-white transition"
                >Books</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/category/mobile-tablet"
                class="text-gray-400 hover:text-white transition"
                >Mobile & Tablets</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/category/software"
                class="text-gray-400 hover:text-white transition"
                >Software</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/category/fashion-beauty"
                class="text-gray-400 hover:text-white transition"
                >Fashion & Beauty</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/category/gaming"
                class="text-gray-400 hover:text-white transition"
                >Gaming</NuxtLink
              >
            </li>
          </ul>
        </div>

        <div>
          <h3 class="text-xl font-bold mb-4">&nbsp;</h3>
          <ul class="space-y-2">
            <li>
              <NuxtLink
                to="/category/sports-fitness"
                class="text-gray-400 hover:text-white transition"
                >Sports & Fitness</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/category/security"
                class="text-gray-400 hover:text-white transition"
                >Security</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/category/camera"
                class="text-gray-400 hover:text-white transition"
                >Camera & Accessories</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/category/health"
                class="text-gray-400 hover:text-white transition"
                >Health</NuxtLink
              >
            </li>
            <li>
              <NuxtLink
                to="/category/kitchen-dining"
                class="text-gray-400 hover:text-white transition"
                >Kitchen & Dining</NuxtLink
              >
            </li>
          </ul>
        </div>
      </div>

      <div
        class="border-t border-gray-800 mt-12 pt-8 text-center text-gray-400"
      >
        <p>© 2025 Online.Com | All rights reserved</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
// Footer component
</script>
