<template>
  <section
    class="hero-section relative bg-green-900 min-h-screen flex flex-col justify-center items-center text-center px-4 py-20 overflow-hidden"
  >
    <!-- Animated Background Circles -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="circle circle-1"></div>
      <div class="circle circle-2"></div>
      <div class="circle circle-3"></div>
      <div class="circle circle-4"></div>
    </div>

    <!-- Content -->
    <div class="relative z-10 max-w-6xl mx-auto">
      <!-- Gradient Headline -->
      <h1
        class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl xl:text-8xl font-black leading-tight mb-4 md:mb-6 animate-fade-in"
      >
        <span class="gradient-yellow">SEARCH</span>
        <span class="gradient-orange"> & </span>
        <span class="gradient-compare">COMPARE</span>
        <br />
        <span class="gradient-yellow">THE BEST</span>
        <span class="gradient-deals"> DEALS</span>
        <span class="gradient-online"> ONLINE</span>
      </h1>

      <!-- Subtitle -->
      <p class="text-gray-700 text-lg md:text-xl lg:text-2xl mb-8 md:mb-12 font-medium animate-fade-in-delay">
        Discover amazing products at unbeatable prices
      </p>

      <!-- Search Box -->
      <div class="w-full max-w-2xl lg:max-w-3xl mx-auto px-4 animate-slide-up">
        <div
          class="flex items-center bg-white/20 backdrop-blur-sm border-2 border-blue-400 rounded-2xl shadow-2xl overflow-hidden hover:border-blue-600 hover:shadow-blue-200/50 transition-all duration-300"
        >
          <input
            v-model="searchQuery"
            type="text"
            placeholder="What are you looking for today?"
            class="flex-1 px-4 sm:px-6 lg:px-8 py-4 sm:py-5 lg:py-6 text-sm sm:text-base lg:text-lg outline-none text-gray-800 placeholder-gray-500 font-medium bg-transparent"
            @keyup.enter="handleSearch"
          />
          <button
            @click="handleSearch"
            class="px-6 sm:px-8 lg:px-10 py-4 sm:py-5 lg:py-6 bg-gradient-to-r from-blue-600 to-purple-600 text-white hover:from-blue-700 hover:to-purple-700 transition-all duration-300 flex-shrink-0 font-semibold text-sm sm:text-base"
            aria-label="Search"
          >
            <svg
              class="w-5 h-5 sm:w-6 sm:h-6 inline-block"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2.5"
                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
              />
            </svg>
          </button>
        </div>
      </div>

      <!-- Popular Categories -->
      <div class="mt-12 animate-fade-in-delay-2">
        <p class="text-gray-600 text-sm md:text-base mb-4 font-medium">Popular Categories:</p>
        <div class="flex flex-wrap justify-center gap-3">
          <button
            @click="searchCategory('smartphones')"
            class="px-4 py-2 bg-white/80 backdrop-blur-sm rounded-full text-sm font-medium text-gray-700 hover:bg-blue-600 hover:text-white transition-all duration-300 shadow-md hover:shadow-lg"
          >
            📱 Smartphones
          </button>
          <button
            @click="searchCategory('laptops')"
            class="px-4 py-2 bg-white/80 backdrop-blur-sm rounded-full text-sm font-medium text-gray-700 hover:bg-purple-600 hover:text-white transition-all duration-300 shadow-md hover:shadow-lg"
          >
            💻 Laptops
          </button>
          <button
            @click="searchCategory('fragrances')"
            class="px-4 py-2 bg-white/80 backdrop-blur-sm rounded-full text-sm font-medium text-gray-700 hover:bg-indigo-600 hover:text-white transition-all duration-300 shadow-md hover:shadow-lg"
          >
            🌸 Fragrances
          </button>
          <button
            @click="searchCategory('furniture')"
            class="px-4 py-2 bg-white/80 backdrop-blur-sm rounded-full text-sm font-medium text-gray-700 hover:bg-pink-600 hover:text-white transition-all duration-300 shadow-md hover:shadow-lg"
          >
            🪑 Furniture
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const searchQuery = ref("");

const handleSearch = () => {
  if (searchQuery.value.trim()) {
    router.push(`/search?q=${encodeURIComponent(searchQuery.value)}`);
  }
};

const searchCategory = (category) => {
  router.push(`/search?category=${encodeURIComponent(category)}`);
};
</script>

<style scoped>
/* Hero Section Background */
.hero-section {
  background: linear-gradient(135deg, #10b981 0%, #34d399 25%, #6ee7b7 50%, #059669 75%, #047857 100%);
  background-size: 400% 400%;
  animation: gradientShift 15s ease infinite;
}

@keyframes gradientShift {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

/* Animated Background Circles */
.circle {
  position: absolute;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(40px);
  animation: float 20s ease-in-out infinite;
}

.circle-1 {
  width: 300px;
  height: 300px;
  top: 10%;
  left: 10%;
  animation-delay: 0s;
}

.circle-2 {
  width: 400px;
  height: 400px;
  top: 50%;
  right: 5%;
  animation-delay: 3s;
}

.circle-3 {
  width: 250px;
  height: 250px;
  bottom: 10%;
  left: 20%;
  animation-delay: 6s;
}

.circle-4 {
  width: 350px;
  height: 350px;
  bottom: 20%;
  right: 15%;
  animation-delay: 9s;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0) rotate(0deg);
    opacity: 0.3;
  }
  50% {
    transform: translateY(-30px) rotate(180deg);
    opacity: 0.6;
  }
}

/* Gradient Text Styles */
.gradient-yellow {
  background: linear-gradient(135deg, #FFD700 0%, #FFC000 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 8px rgba(255, 215, 0, 0.4));
}

.gradient-orange {
  background: linear-gradient(135deg, #FF8C42 0%, #FF6B35 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 8px rgba(255, 107, 53, 0.4));
}

.gradient-compare {
  background: linear-gradient(90deg, #9333EA 0%, #7C3AED 30%, #6366F1 60%, #3B82F6 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 8px rgba(124, 58, 237, 0.4));
}

.gradient-deals {
  background: linear-gradient(135deg, #EC4899 0%, #DB2777 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 8px rgba(236, 72, 153, 0.4));
}

.gradient-online {
  background: linear-gradient(135deg, #3B82F6 0%, #2563EB 100%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  filter: drop-shadow(0 2px 8px rgba(59, 130, 246, 0.4));
}

/* Animations */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fadeIn 1s ease-out;
}

.animate-fade-in-delay {
  animation: fadeIn 1s ease-out 0.3s backwards;
}

.animate-fade-in-delay-2 {
  animation: fadeIn 1s ease-out 0.6s backwards;
}

.animate-slide-up {
  animation: slideUp 1s ease-out 0.4s backwards;
}
</style>
