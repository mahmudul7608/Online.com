<template>
  <section class="py-16 bg-gradient-to-br from-purple-50 to-pink-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <!-- Left: Video Section -->
        <div class="relative group">
          <!-- Video Thumbnail -->
          <video
            src="/videos/shortVideo.mp4"
            poster="/videos/shortVideo.mp4"
            controls
            class="w-full rounded-lg shadow-2xl"
          ></video>

          <!-- Optional overlay Play Button (if you want a custom play UI instead of default controls) -->
          <!--
          <div
            class="absolute inset-0 flex items-center justify-center bg-black/30 rounded-lg opacity-0 group-hover:opacity-100 transition"
          >
            <button
              @click="playVideo"
              class="bg-white text-purple-600 p-4 rounded-full shadow-lg hover:bg-purple-100 transition"
            >
              ▶
            </button>
          </div>
          -->
        </div>

        <!-- Right: Text Section -->
        <div>
          <h2 class="text-4xl font-extrabold text-gray-900 mb-6 leading-snug">
            SMART COMPARISON SHOPPING <br />
            WITH <span class="text-purple-600">Online.com</span>
          </h2>
          <p class="text-lg text-gray-700 mb-8">
            Online.com lists thousands of products from top Bangladesh eCommerce
            like Daraz, Othoba, Pickaboo, Chaldal, AjkerDeal, and more. No more
            worrying about price variations — our smart algorithm helps you find
            the best deal at the lowest price.
          </p>
          <NuxtLink
            to="/search"
            class="inline-block bg-gradient-to-r from-purple-600 to-pink-500 text-white px-8 py-4 rounded-lg hover:from-purple-700 hover:to-pink-600 transition-all duration-300 text-lg font-semibold shadow-md hover:shadow-lg"
          >
            🔍 Search Now
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// You can add JS functions for custom video controls if needed
</script>
