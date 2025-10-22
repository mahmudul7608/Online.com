<template>
  <div class="min-h-screen bg-white pt-16">
    <Header />

    <!-- Hero Section -->
    <section
      class="min-h-screen bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200 flex items-center justify-center relative overflow-hidden"
    >
      <!-- Decorative Background Elements -->
      <!-- Animated gradient blobs -->
      <div
        class="absolute top-10 left-10 w-72 h-72 bg-purple-400/40 rounded-full blur-3xl animate-pulse"
      ></div>
      <div
        class="absolute bottom-10 right-10 w-96 h-96 bg-pink-400/30 rounded-full blur-3xl animate-pulse"
        style="animation-delay: 1s"
      ></div>

      <!-- Decorative shapes -->
      <div
        class="absolute top-20 right-1/4 w-16 h-16 border-4 border-purple-400/30 rotate-45 animate-spin-slow"
      ></div>
      <div
        class="absolute bottom-32 left-1/4 w-12 h-12 bg-purple-500/20 rounded-full animate-bounce-slow"
      ></div>
      <div
        class="absolute top-1/3 left-10 w-8 h-8 bg-pink-500/30 transform rotate-45"
      ></div>
      <div
        class="absolute top-1/2 right-20 w-6 h-6 bg-purple-600/40 rounded-full"
      ></div>

      <!-- Decorative leaf-like shapes -->
      <svg
        class="absolute top-1/4 left-1/3 w-32 h-32 text-purple-600/20 animate-float"
        viewBox="0 0 100 100"
        fill="currentColor"
      >
        <path
          d="M50,10 Q80,30 70,60 Q60,90 30,80 Q10,70 20,40 Q30,10 50,10 Z"
        />
      </svg>
      <svg
        class="absolute bottom-1/4 right-1/3 w-40 h-40 text-purple-700/15 animate-float"
        style="animation-delay: 2s"
        viewBox="0 0 100 100"
        fill="currentColor"
      >
        <path
          d="M50,10 Q80,30 70,60 Q60,90 30,80 Q10,70 20,40 Q30,10 50,10 Z"
        />
      </svg>

      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 w-full relative z-10">
        <!-- Small top badge - Centered at top -->
        <div class="flex justify-center mb-8">
          <div
            class="inline-block bg-purple-600/10 backdrop-blur-sm px-6 py-2 rounded-full border-2 border-purple-400/50"
          >
            <p class="text-sm md:text-base text-purple-800 font-semibold">
              Looking to Find Best Deals Online?
            </p>
          </div>
        </div>

        <div class="grid lg:grid-cols-2 gap-8 lg:gap-12 items-center">
          <!-- Left Side: Text Content -->
          <div
            class="text-center lg:text-left order-2 lg:order-1 flex flex-col justify-center"
          >
            <!-- Main Heading with Beautiful Typography -->
            <div class="space-y-2">
              <h1
                class="text-5xl sm:text-6xl md:text-7xl lg:text-8xl font-black leading-none"
              >
                <span class="block text-gray-900 mb-1">We Find</span>
                <span
                  class="block bg-gradient-to-r from-purple-600 via-pink-600 to-purple-700 bg-clip-text text-transparent drop-shadow-2xl mb-1"
                  style="-webkit-text-stroke: 0.5px rgba(147, 51, 234, 0.1)"
                  >BEST DEALS</span
                >
                <span class="block text-gray-900">FOR YOU</span>
              </h1>

              <!-- Decorative underline -->
              <div class="flex justify-center lg:justify-start mt-6">
                <div
                  class="w-40 h-2 bg-gradient-to-r from-purple-600 via-pink-500 to-purple-600 rounded-full shadow-lg"
                ></div>
              </div>
            </div>
          </div>

          <!-- Right Side: Video with Decorative Frame -->
          <div
            class="order-1 lg:order-2 flex justify-center items-center relative"
          >
            <!-- Decorative background for video -->
            <div class="relative group">
              <!-- Animated glow effect -->
              <div
                class="absolute -inset-4 bg-gradient-to-r from-purple-600 to-pink-600 rounded-3xl blur-2xl opacity-30 group-hover:opacity-50 animate-pulse"
              ></div>

              <!-- Video container with modern frame -->
              <div
                class="relative bg-white p-3 sm:p-4 rounded-3xl shadow-2xl transform group-hover:scale-105 transition-all duration-500"
              >
                <!-- Inner decorative border -->
                <div
                  class="bg-gradient-to-br from-purple-200 to-pink-200 p-1 rounded-2xl"
                >
                  <video
                    src="/public/videos/mekup33.mp4"
                    autoplay
                    loop
                    muted
                    playsinline
                    class="rounded-2xl shadow-xl w-[600px] max-w-[280px] sm:max-w-[350px] md:max-w-[450px] lg:max-w-[500px] h-auto object-cover"
                  ></video>
                </div>

                <!-- Decorative corner accents -->
                <div
                  class="absolute -top-3 -left-3 w-8 h-8 bg-purple-600 rounded-full animate-ping opacity-75"
                ></div>
                <div
                  class="absolute -bottom-3 -right-3 w-10 h-10 bg-pink-600 rounded-full animate-ping opacity-75"
                  style="animation-delay: 0.5s"
                ></div>
              </div>

              <!-- Floating decorative elements around video -->
              <div
                class="absolute -top-6 -right-6 w-12 h-12 bg-yellow-400 rounded-full animate-bounce opacity-80"
              ></div>
              <div
                class="absolute -bottom-8 -left-8 w-16 h-16 bg-purple-500/30 rounded-full blur-xl animate-pulse"
              ></div>
            </div>
          </div>
        </div>

        <!-- Search Input - Centered between text and video -->
        <div class="max-w-lg mx-auto mt-12 mb-8">
          <div
            class="flex items-center bg-white rounded-full shadow-2xl overflow-hidden relative border-2 border-purple-300 hover:border-purple-400 transition-all"
          >
            <input
              v-model="searchQuery"
              type="text"
              placeholder="What Are You Looking For Today?"
              class="flex-1 px-5 py-2.5 text-sm outline-none text-center text-gray-700 placeholder:text-gray-500 font-medium"
              @keyup.enter="handleSearch"
            />
            <button
              v-if="searchQuery"
              @click="clearSearch"
              class="absolute right-28 text-gray-400 hover:text-gray-600 transition px-2"
              title="Clear search"
            >
              <svg
                class="w-4 h-4"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M6 18L18 6M6 6l12 12"
                />
              </svg>
            </button>
            <button
              @click="handleSearch"
              class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-6 py-2.5 hover:from-purple-700 hover:to-pink-700 transition-all font-bold text-sm rounded-full shadow-lg hover:shadow-xl"
            >
              Search
            </button>
          </div>

          <!-- Star Rating below search -->
          <div class="flex items-center justify-center gap-2 mt-5">
            <div
              class="inline-flex items-center gap-2 bg-white/80 px-5 py-2 rounded-full border-2 border-purple-300 shadow-md"
            >
              <div class="flex text-yellow-400 text-base">
                <span>⭐</span>
                <span>⭐</span>
                <span>⭐</span>
                <span>⭐</span>
                <span>⭐</span>
              </div>
              <span class="text-xs text-gray-700 font-bold">515+ 5 Stars</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Smart Comparison Section -->

    <section
      class="py-20 bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200"
    >
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <!-- Left: Text content -->
          <div class="order-1 md:order-1 text-center md:text-left">
            <h2
              class="text-4xl md:text-5xl font-extrabold text-gray-900 mb-6 leading-tight"
            >
              SMART SHOPPING <br />
              WITH <span class="text-pink-600">Online.Com</span>
            </h2>
            <p class="text-lg text-gray-700 mb-8 leading-relaxed">
              Online.com lists thousands of products from top Bangladesh
              eCommerce sites like Daraz, Othoba, Pickaboo, Chaldal, AjkerDeal,
              and more. No more confusion or price variation! Our intelligent
              comparison algorithm helps you find the <b>best deals</b> at the
              <b>lowest price</b>.
            </p>
            <button
              @click="scrollToSearch"
              class="bg-gradient-to-r from-pink-500 to-pink-600 text-white px-10 py-4 rounded-xl font-bold text-lg shadow-lg hover:shadow-xl hover:from-pink-600 hover:to-pink-700 transition-all duration-300"
            >
              Search Now
            </button>
          </div>

          <!-- Right: Video -->
          <div class="order-2 md:order-2 flex justify-center">
            <video
              src="/videos/shortVideo.mp4"
              autoplay
              loop
              muted
              playsinline
              class="rounded-2xl shadow-3xl w-full max-w-md md:max-w-lg"
            ></video>
          </div>
        </div>
      </div>
    </section>

    <!-- Browse Top Categories - Product Cards -->
    <section
      class="py-20 bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200"
    >
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-4xl font-bold text-center text-gray-900 mb-12">
          BROWSE TOP CATEGORIES
        </h2>

        <!-- Cart Button -->
        <button
          @click="toggleCart"
          class="fixed bottom-6 right-6 z-50 bg-green-600 text-white p-4 rounded-full shadow-2xl hover:bg-green-700 transition-all hover:scale-110"
        >
          <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"
            />
          </svg>
          <span
            v-if="cartItemCount > 0"
            class="absolute -top-2 -right-2 bg-red-600 text-white text-xs font-bold rounded-full w-6 h-6 flex items-center justify-center"
          >
            {{ cartItemCount }}
          </span>
        </button>

        <!-- Cart Sidebar -->
        <div v-if="showCart" class="fixed inset-0 z-50 overflow-hidden">
          <div
            class="absolute inset-0 bg-black bg-opacity-50"
            @click="toggleCart"
          ></div>
          <div
            class="absolute right-0 top-0 bottom-0 w-full max-w-md bg-white shadow-2xl overflow-y-auto"
          >
            <div class="p-6">
              <div class="flex justify-between items-center mb-6">
                <h2 class="text-2xl font-bold text-gray-900">Shopping Cart</h2>
                <button
                  @click="toggleCart"
                  class="text-gray-500 hover:text-gray-700"
                >
                  <svg
                    class="w-6 h-6"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M6 18L18 6M6 6l12 12"
                    />
                  </svg>
                </button>
              </div>

              <!-- Cart Items -->
              <div v-if="cart.length === 0" class="text-center py-12">
                <p class="text-gray-500 text-lg">Your cart is empty</p>
              </div>
              <div v-else>
                <div
                  v-for="item in cart"
                  :key="item.id"
                  class="flex items-center gap-4 mb-4 pb-4 border-b"
                >
                  <img
                    :src="item.image"
                    :alt="item.name"
                    class="w-20 h-20 object-cover rounded"
                  />
                  <div class="flex-1">
                    <h3 class="font-semibold text-sm">{{ item.name }}</h3>
                    <p class="text-green-600 font-bold">{{ item.price }} TK</p>
                    <div class="flex items-center gap-2 mt-2">
                      <button
                        @click="updateQuantity(item.id, -1)"
                        class="px-2 py-1 bg-gray-200 rounded hover:bg-gray-300"
                      >
                        -
                      </button>
                      <span class="font-semibold">{{ item.quantity }}</span>
                      <button
                        @click="updateQuantity(item.id, 1)"
                        class="px-2 py-1 bg-gray-200 rounded hover:bg-gray-300"
                      >
                        +
                      </button>
                      <button
                        @click="removeFromCart(item.id)"
                        class="ml-auto text-red-600 hover:text-red-700"
                      >
                        <svg
                          class="w-5 h-5"
                          fill="none"
                          stroke="currentColor"
                          viewBox="0 0 24 24"
                        >
                          <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16"
                          />
                        </svg>
                      </button>
                    </div>
                  </div>
                </div>

                <!-- Cart Summary -->
                <div class="mt-6 space-y-3 border-t pt-4">
                  <div class="flex justify-between text-gray-700">
                    <span>Subtotal:</span>
                    <span class="font-semibold"
                      >{{ cartSubtotal.toLocaleString() }} TK</span
                    >
                  </div>
                  <div class="flex justify-between text-gray-700">
                    <span>VAT (15%):</span>
                    <span class="font-semibold"
                      >{{ cartVAT.toLocaleString() }} TK</span
                    >
                  </div>
                  <div
                    class="flex justify-between text-xl font-bold text-gray-900 border-t pt-3"
                  >
                    <span>Total:</span>
                    <span class="text-green-600"
                      >{{ cartTotal.toLocaleString() }} TK</span
                    >
                  </div>
                  <button
                    class="w-full bg-gradient-to-r from-green-600 to-emerald-600 text-white py-4 rounded-xl hover:from-green-700 hover:to-emerald-700 transition-all font-semibold text-lg mt-4"
                  >
                    Checkout
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Product Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
          <div
            v-for="product in topProducts"
            :key="product.id"
            class="bg-white rounded-2xl shadow-lg overflow-hidden hover:shadow-2xl transition-all duration-300 hover:-translate-y-2 group border border-blue-400"
          >
            <!-- Product Image -->
            <div
              class="relative h-52 bg-gray-50 flex items-center justify-center p-3 overflow-hidden"
            >
              <img
                :src="product.image"
                :alt="product.name"
                class="max-h-full max-w-full object-contain group-hover:scale-110 transition-transform duration-300"
              />
              <div
                class="absolute top-3 right-3 bg-green-600 text-white px-3 py-1 rounded-full text-xs font-semibold"
              >
                {{ product.category }}
              </div>
            </div>

            <!-- Product Info -->
            <div class="p-5">
              <h3
                class="text-lg font-semibold text-gray-900 mb-2 line-clamp-2 min-h-[3.5rem]"
              >
                {{ product.name }}
              </h3>

              <div class="flex items-center mb-3">
                <div class="flex items-center text-yellow-500 mr-2">
                  <span class="mr-1">⭐</span>
                  <span class="text-sm font-semibold">4.5</span>
                </div>
                <span class="text-gray-500 text-xs">({{ product.store }})</span>
              </div>

              <!-- Price -->
              <div class="mb-4">
                <span class="text-2xl font-bold text-green-600"
                  >{{ product.price }} TK</span
                >
              </div>

              <!-- Add to Cart Button -->
              <button
                @click="addToCart(product)"
                class="w-full px-4 py-3 bg-gradient-to-r from-green-600 to-emerald-600 text-white rounded-lg hover:from-green-700 hover:to-emerald-700 transition-all text-sm font-semibold shadow-md hover:shadow-lg"
              >
                🛒 Add to Cart
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Extension Section -->
    <section
      class="py-24 bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200 relative overflow-hidden"
    >
      <!-- Decorative Background Elements -->
      <div
        class="absolute top-20 left-10 w-64 h-64 bg-purple-300/20 rounded-full blur-3xl"
      ></div>
      <div
        class="absolute bottom-20 right-10 w-80 h-80 bg-pink-300/20 rounded-full blur-3xl"
      ></div>

      <div class="max-w-7xl mx-auto px-6 lg:px-8 relative z-10">
        <!-- Section Header -->
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-black text-gray-900 mb-4">
            Browser Extension
          </h2>
        </div>

        <div class="grid md:grid-cols-2 gap-16 items-center">
          <!-- Left: Text Content -->
          <div class="text-center md:text-left space-y-6">
            <h3
              class="text-3xl md:text-4xl font-extrabold text-gray-900 leading-tight"
            >
              Shop Smarter with
              <span
                class="block bg-gradient-to-r from-purple-600 via-pink-600 to-purple-700 bg-clip-text text-transparent"
              >
                Online.Com Extension
              </span>
            </h3>

            <div class="space-y-4">
              <div class="flex items-start gap-4">
                <div
                  class="flex-shrink-0 w-10 h-10 bg-gradient-to-br from-purple-500 to-pink-500 rounded-full flex items-center justify-center text-white font-bold shadow-lg"
                >
                  ✓
                </div>
                <div class="text-left">
                  <h4 class="font-bold text-gray-900 text-lg">
                    Instant Price Comparison
                  </h4>
                  <p class="text-gray-600">
                    Compare prices from all major e-commerce sites in one click
                  </p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div
                  class="flex-shrink-0 w-10 h-10 bg-gradient-to-br from-purple-500 to-pink-500 rounded-full flex items-center justify-center text-white font-bold shadow-lg"
                >
                  ✓
                </div>
                <div class="text-left">
                  <h4 class="font-bold text-gray-900 text-lg">
                    Best Deal Alerts
                  </h4>
                  <p class="text-gray-600">
                    Get notified when prices drop on your favorite items
                  </p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div
                  class="flex-shrink-0 w-10 h-10 bg-gradient-to-br from-purple-500 to-pink-500 rounded-full flex items-center justify-center text-white font-bold shadow-lg"
                >
                  ✓
                </div>
                <div class="text-left">
                  <h4 class="font-bold text-gray-900 text-lg">
                    Save Time & Money
                  </h4>
                  <p class="text-gray-600">
                    Shop confidently knowing you're getting the best deal
                  </p>
                </div>
              </div>
            </div>

            <div class="pt-4">
              <div
                class="inline-flex items-center gap-3 bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-4 rounded-2xl font-bold text-lg shadow-2xl"
              >
                <span class="text-2xl">🚀</span>
                <span>Coming Soon</span>
              </div>
            </div>
          </div>

          <!-- Right: Video -->
          <div class="flex justify-center relative group">
            <div
              class="absolute -inset-6 bg-gradient-to-r from-purple-400 to-pink-400 rounded-3xl blur-2xl opacity-30 group-hover:opacity-50 transition duration-500 animate-pulse"
            ></div>
            <div class="relative z-10 bg-white p-2 rounded-3xl shadow-2xl">
              <video
                src="/videos/ShortVideo2.mp4"
                autoplay
                muted
                loop
                playsinline
                class="rounded-2xl w-[280px] h-[400px] object-cover group-hover:scale-105 transition-all duration-500"
              ></video>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 💬 Customer Reviews Section -->
    <section
      class="py-20 bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200"
    >
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Heading -->
        <h2
          class="text-4xl font-bold text-center text-gray-900 mb-14 tracking-wide"
        >
          CUSTOMER REVIEWS
        </h2>

        <!-- Review Cards -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <!-- Card 1 -->
          <div
            class="bg-gradient-to-br from-slate-800/90 to-slate-900/90 backdrop-blur-sm rounded-2xl p-6 shadow-2xl hover:shadow-purple-500/30 transition-all duration-300 border border-slate-700/50 hover:border-purple-500/50"
          >
            <!-- Stars at top -->
            <div class="flex space-x-1 mb-4">
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
            </div>

            <!-- Review Text -->
            <p class="text-gray-300 text-sm italic leading-relaxed mb-6">
              "Online.Com completely transformed my job search. I found my dream
              job within two weeks of using the platform!"
            </p>

            <!-- User Info -->
            <div class="flex items-center gap-3">
              <img
                src="/images/testi1.jpg"
                alt="Sarah Johnson"
                class="w-12 h-12 rounded-full object-cover shadow-lg ring-2 ring-purple-300"
              />
              <div>
                <h3 class="text-white font-semibold">Sarah Johnson</h3>
                <p class="text-gray-400 text-sm">
                  Software Developer at TechCorp
                </p>
              </div>
            </div>
          </div>

          <!-- Card 2 -->
          <div
            class="bg-gradient-to-br from-slate-800/90 to-slate-900/90 backdrop-blur-sm rounded-2xl p-6 shadow-2xl hover:shadow-purple-500/30 transition-all duration-300 border border-slate-700/50 hover:border-purple-500/50"
          >
            <!-- Stars at top -->
            <div class="flex space-x-1 mb-4">
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
            </div>

            <!-- Review Text -->
            <p class="text-gray-300 text-sm italic leading-relaxed mb-6">
              "The intelligent matching system connected me with opportunities I
              wouldn't have found anywhere else."
            </p>

            <!-- User Info -->
            <div class="flex items-center gap-3">
              <img
                src="/images/testi2.jpg"
                alt="Michael Chen"
                class="w-12 h-12 rounded-full object-cover shadow-lg ring-2 ring-purple-300"
              />
              <div>
                <h3 class="text-white font-semibold">Michael Chen</h3>
                <p class="text-gray-400 text-sm">
                  Product Manager at InnovateCo
                </p>
              </div>
            </div>
          </div>

          <!-- Card 3 -->
          <div
            class="bg-gradient-to-br from-slate-800/90 to-slate-900/90 backdrop-blur-sm rounded-2xl p-6 shadow-2xl hover:shadow-purple-500/30 transition-all duration-300 border border-slate-700/50 hover:border-purple-500/50"
          >
            <!-- Stars at top -->
            <div class="flex space-x-1 mb-4">
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-yellow-400 text-xl">★</span>
              <span class="text-gray-600 text-xl">★</span>
            </div>

            <!-- Review Text -->
            <p class="text-gray-300 text-sm italic leading-relaxed mb-6">
              "The application process was seamless, and the employer responses
              were incredibly fast. Highly recommend!"
            </p>

            <!-- User Info -->
            <div class="flex items-center gap-3">
              <img
                src="/images/testi3.jpg"
                alt="Emily Rodriguez"
                class="w-12 h-12 rounded-full object-cover shadow-lg ring-2 ring-purple-300"
              />
              <div>
                <h3 class="text-white font-semibold">Emily Rodriguez</h3>
                <p class="text-gray-400 text-sm">UX Designer at DesignStudio</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 🎬 Local Video Section -->
    <section
      class="py-20 bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200"
    >
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Video Wrapper -->
        <div
          class="relative max-w-4xl mx-auto overflow-hidden rounded-2xl shadow-2xl group"
        >
          <video
            controls
            autoplay
            muted
            loop
            class="w-full h-[350px] object-cover transition-transform duration-500 group-hover:scale-105"
          >
            <source src="/videos/short.mp4" type="video/mp4" />
            Your browser does not support the video tag.
          </video>

          <!-- Optional overlay gradient for style -->
          <div
            class="absolute inset-0 bg-gradient-to-t from-black/30 via-transparent to-transparent pointer-events-none"
          ></div>
        </div>

        <!-- Title -->
        <h3
          class="text-3xl font-bold text-center text-gray-900 mt-10 tracking-wide"
        >
          MOST POPULAR PRODUCTS
        </h3>
      </div>
    </section>

    <!-- Newsletter -->
    <section
      class="py-20 bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200"
    >
      <div class="max-w-4xl mx-auto px-4 text-center">
        <h2 class="text-4xl font-bold mb-6 text-gray-900">
          GET THE BEST ONLINE <br />
          DEALS ON YOUR INBOX
        </h2>
        <p class="text-xl mb-8 text-gray-700">
          Signup Our Newsletter And Receive Periodic Info And Alerts <br />
          On Best Online Deals In Bangladesh
        </p>
        <form class="flex flex-col md:flex-row gap-4 max-w-2xl mx-auto">
          <input
            type="email"
            placeholder="Input your email here"
            class="flex-1 px-6 py-4 rounded-lg text-gray-900 outline-none"
          />
          <button
            type="submit"
            class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-4 rounded-lg font-semibold hover:from-purple-700 hover:to-pink-700 transition shadow-lg"
          >
            Submit
          </button>
        </form>
      </div>
    </section>

    <FooterSection />
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const searchQuery = ref("");
const cart = ref([]);
const showCart = ref(false);

const VAT_RATE = 0.15; // 15% VAT

const handleSearch = () => {
  if (searchQuery.value.trim()) {
    router.push(`/search?q=${encodeURIComponent(searchQuery.value)}`);
  } else {
    router.push("/search");
  }
};

const clearSearch = () => {
  searchQuery.value = "";
};

const scrollToSearch = () => {
  const searchSection = document.querySelector('input[type="text"]');
  if (searchSection) {
    searchSection.scrollIntoView({ behavior: "smooth", block: "center" });
    searchSection.focus();
  }
};

const addToCart = (product) => {
  const existingItem = cart.value.find((item) => item.id === product.id);

  if (existingItem) {
    existingItem.quantity++;
  } else {
    cart.value.push({
      id: product.id,
      name: product.name,
      price: parseFloat(product.price.replace(/,/g, "")),
      image: product.image,
      quantity: 1,
    });
  }

  showCart.value = true;
};

const removeFromCart = (productId) => {
  cart.value = cart.value.filter((item) => item.id !== productId);
};

const updateQuantity = (productId, change) => {
  const item = cart.value.find((item) => item.id === productId);
  if (item) {
    item.quantity += change;
    if (item.quantity <= 0) {
      removeFromCart(productId);
    }
  }
};

const toggleCart = () => {
  showCart.value = !showCart.value;
};

const cartSubtotal = computed(() => {
  return cart.value.reduce((sum, item) => sum + item.price * item.quantity, 0);
});

const cartVAT = computed(() => {
  return Math.round(cartSubtotal.value * VAT_RATE);
});

const cartTotal = computed(() => {
  return cartSubtotal.value + cartVAT.value;
});

const cartItemCount = computed(() => {
  return cart.value.reduce((sum, item) => sum + item.quantity, 0);
});

const categories = [
  { name: "Book", icon: "https://mullokoto.com/category-icon/book.svg" },
  {
    name: "Mobile, Tablet & Accessories",
    icon: "https://mullokoto.com/category-icon/smartphone.svg",
  },
  {
    name: "Computer, Laptop & Accessories",
    icon: "https://mullokoto.com/category-icon/laptop.svg",
  },
  {
    name: "Software",
    icon: "https://mullokoto.com/category-icon/software.svg",
  },
  {
    name: "Fashion & Beauty",
    icon: "https://mullokoto.com/category-icon/fashion.svg",
  },
  { name: "Gaming", icon: "https://mullokoto.com/category-icon/gaming.svg" },
  {
    name: "Home Application",
    icon: "https://mullokoto.com/category-icon/applience.svg",
  },
  {
    name: "Home Electrical & Electronics",
    icon: "https://mullokoto.com/category-icon/home-appliance.svg",
  },
  {
    name: "Construction & Tools",
    icon: "https://mullokoto.com/category-icon/construction.svg",
  },
  { name: "Baby & Toys", icon: "https://mullokoto.com/category-icon/baby.svg" },
  {
    name: "Kitchen & Dining",
    icon: "https://mullokoto.com/category-icon/kitchen.svg",
  },
  {
    name: "Food & Groceries",
    icon: "https://mullokoto.com/category-icon/food.svg",
  },
  {
    name: "Sports & Fitness",
    icon: "https://mullokoto.com/category-icon/sport.svg",
  },
  {
    name: "Security",
    icon: "https://mullokoto.com/category-icon/security.svg",
  },
  { name: "Bike & Cars", icon: "https://mullokoto.com/category-icon/bike.svg" },
  {
    name: "Camera & Accessories",
    icon: "https://mullokoto.com/category-icon/camera.svg",
  },
  {
    name: "Gadgets & Stationary",
    icon: "https://mullokoto.com/category-icon/gadget.svg",
  },
  {
    name: "Cooking Materials",
    icon: "https://mullokoto.com/category-icon/cooking.svg",
  },
  { name: "Gift", icon: "https://mullokoto.com/category-icon/gift.svg" },
  {
    name: "Travel & Accessories",
    icon: "https://mullokoto.com/category-icon/travel.svg",
  },
  { name: "Office", icon: "https://mullokoto.com/category-icon/office.svg" },
  { name: "Pets", icon: "https://mullokoto.com/category-icon/pet.svg" },
  {
    name: "Health",
    icon: "https://mullokoto.com/category-icon/first-aid-kit.svg",
  },
  { name: "Service", icon: "https://mullokoto.com/category-icon/service.svg" },
];

const topProducts = [
  {
    id: 101,
    name: "Samsung Galaxy S23 Ultra 5G",
    price: "135,000",
    image: "/images/s23.jpg",
    store: "Othoba",
    category: "Mobile",
  },
  {
    id: 102,
    name: "Apple iPhone 14 Pro Max",
    price: "165,000",
    image: "/images/apple-iphone-14.jpg",
    store: "Ryans",
    category: "Mobile",
  },
  {
    id: 103,
    name: 'MacBook Air M2 13.6" 8GB 256GB',
    price: "125,000",
    image: "/images/MacBook Air M2 .jpg",
    store: "Ryans",
    category: "Laptop",
  },
  {
    id: 104,
    name: "Sony WH-1000XM5 Wireless Headphones",
    price: "35,000",
    image: "/images/Sony .jpg",
    store: "Othoba",
    category: "Audio",
  },
  {
    id: 105,
    name: "Canon EOS R6 Mark II Mirrorless",
    price: "280,000",
    image: "/images/dell-xps g.jpg",
    store: "Ryans",
    category: "Camera",
  },
  {
    id: 106,
    name: 'Samsung 55" 4K Smart TV',
    price: "68,000",
    image: "/images/iPad Pro .jpg",
    store: "Othoba",
    category: "TV",
  },
  {
    id: 107,
    name: "Dell XPS 15 9520 Intel Core i7",
    price: "185,000",
    image: "/images/dell-xps g.jpg",
    store: "Ryans",
    category: "Laptop",
  },
  {
    id: 108,
    name: 'iPad Pro 12.9" M2 Chip',
    price: "145,000",
    image: "/images/iPad Pro .jpg",
    store: "Ryans",
    category: "Tablet",
  },
  {
    id: 109,
    name: "Nikon Z9 Mirrorless Camera",
    price: "520,000",
    image: "/images/s23.jpg",
    store: "Ryans",
    category: "Camera",
  },
  {
    id: 110,
    name: 'LG 65" OLED 4K Smart TV',
    price: "195,000",
    image: "/images/apple-iphone-14.jpg",
    store: "Othoba",
    category: "TV",
  },
  {
    id: 111,
    name: "Asus ROG Strix Gaming Laptop",
    price: "215,000",
    image: "/images/MacBook Air M2 .jpg",
    store: "Ryans",
    category: "Gaming",
  },
  {
    id: 112,
    name: "Apple Watch Series 9 GPS",
    price: "45,000",
    image: "/images/Sony .jpg",
    store: "Ryans",
    category: "Watch",
  },
];

const featuredProducts = [
  {
    id: 1,
    name: "Canon EOS 90D camera body with EF-S 18-135mm",
    price: "140,000 TK",
    image:
      "https://www.cloud.ryanscomputers.com/cdn/products/small/canon-eos-90d-camera-body-with-ef-s-18-135mm-11574775657.webp",
    store: "Ryans",
    category: "Camera & Accessories",
  },
  {
    id: 2,
    name: "Canon EOS 90D camera body with EF-S 18-135mm",
    price: "140,000 TK",
    image:
      "https://www.cloud.ryanscomputers.com/cdn/products/small/canon-eos-90d-camera-body-with-ef-s-18-135mm-11574775657.webp",
    store: "Ryans",
    category: "Camera & Accessories",
  },
  {
    id: 3,
    name: 'VISION 75" LED 3D 4K H01 Smart',
    price: "160,000 TK",
    image:
      "https://images.othoba.com/images/thumbs/0363665_vision-75-led-tv-3d-4k-h01-smart_300.jpeg",
    store: "Othoba",
    category: "Home Appliances",
  },
  {
    id: 4,
    name: 'VISION 75" LED 3D 4K H01 Smart',
    price: "160,000 TK",
    image:
      "https://images.othoba.com/images/thumbs/0363665_vision-75-led-tv-3d-4k-h01-smart_300.jpeg",
    store: "Othoba",
    category: "Home Appliances",
  },
  {
    id: 5,
    name: "TVS Apache RTR 160 4v Blue Double Disc",
    price: "223,999 TK",
    image:
      "https://images.othoba.com/images/thumbs/0136679_tvs-apache-rtr-160-4v-blue-double-disc_300.jpeg",
    store: "Othoba",
    category: "Bikes & Cars",
  },
  {
    id: 6,
    name: "TVS Apache RTR 160 4v Blue Double Disc",
    price: "223,999 TK",
    image:
      "https://images.othoba.com/images/thumbs/0136679_tvs-apache-rtr-160-4v-blue-double-disc_300.jpeg",
    store: "Othoba",
    category: "Bikes & Cars",
  },
  {
    id: 7,
    name: 'Apple MacBook Pro (Late 2021) Apple M1 Max 16"',
    price: "360,000 TK",
    image:
      "https://www.cloud.ryanscomputers.com/cdn/products/small/apple-macbook-pro-late-2021-apple-m1-max-162-11636265644.webp",
    store: "Ryans",
    category: "Computer, Laptops & Accessories",
  },
  {
    id: 8,
    name: 'Apple MacBook Pro (Late 2021) Apple M1 Max 16"',
    price: "360,000 TK",
    image:
      "https://www.cloud.ryanscomputers.com/cdn/products/small/apple-macbook-pro-late-2021-apple-m1-max-162-11636265644.webp",
    store: "Ryans",
    category: "Computer, Laptops & Accessories",
  },
];

const testimonials = [
  {
    name: "SAIFUL AZAD",
    role: "Cloud Engineer",
    image: "https://mullokoto.com/image/saiful.jpg",
    text: "In the context of Bangladesh, finding a suitable product at reasonable pricing is challenging. Being informed about pricing of the same product in different merchants leverages customer satisfaction and negotiation to impact personal finance positively. Mullo-koto satisfies those demands. Now, before purchasing, I can motivate myself to deal the best.",
  },
  {
    name: "NAZMUS SAKIB",
    role: "Entrepreneur",
    image: "https://mullokoto.com/image/sakib.jpg",
    text: "As we don't have Amazon or Walmart it's hard to find better deals. Then I came across Mullokoto, where thousands of products are listed on multiple e-commerce sites. Here I can search and sort products and compare what I want to buy, they even added a wish list option. I am reassured that the best deal is a search away.",
  },
  {
    name: "POLASH AHMAD",
    role: "Software Developer",
    image: "https://mullokoto.com/image/polash.jpg",
    text: "In the context of Bangladesh, finding a suitable product at reasonable pricing is challenging. Being informed about pricing of the same product in different merchants leverages customer satisfaction and negotiation to impact personal finance positively. Mullo-koto satisfies those demands. Now, before purchasing, best.",
  },
];
</script>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

/* Custom Animations */
@keyframes float {
  0%,
  100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-20px) rotate(5deg);
  }
}

@keyframes spin-slow {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes bounce-slow {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.animate-spin-slow {
  animation: spin-slow 20s linear infinite;
}

.animate-bounce-slow {
  animation: bounce-slow 3s ease-in-out infinite;
}
</style>
