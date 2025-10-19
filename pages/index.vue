<template>
  <div class="min-h-screen bg-white">
    <Header />

    <!-- Hero Section -->
    <section
      class="min-h-screen bg-gradient-to-br from-blue-50 via-purple-50 to-pink-50 flex items-center justify-center relative overflow-hidden"
    >
      <!-- Soft gradient blur circles for background effect -->
      <div
        class="absolute top-14 left-20 w-96 h-96 bg-blue-500/30 rounded-full blur-3xl"
      ></div>
      <div
        class="absolute bottom-20 right-20 w-96 h-96 bg-purple-500/30 rounded-full blur-3xl"
      ></div>
      <div
        class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-pink-300/20 rounded-full blur-3xl"
      ></div>

      <div
        class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center w-full relative z-10"
      >
        <!-- Small top text -->
        <div
          class="inline-block bg-blue-100/50 backdrop-blur-sm px-6 py-2 rounded-full mb-6 border border-blue-400"
        >
          <p class="text-sm md:text-base text-blue-700 font-medium">
            Looking to Find Best Deals Online?
          </p>
        </div>

        <!-- Main heading -->
        <h2 class="text-5xl md:text-7xl lg:text-8xl font-bold mb-2">
          <span class="text-gray-900">We Find </span>
          <span
            class="bg-gradient-to-r from-purple-600 to-blue-600 bg-clip-text text-transparent"
            >BEST DEALS</span
          >
        </h2>

        <!-- Subheading -->
        <h2
          class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-2"
        >
          FOR YOU
        </h2>

        <!-- Search Input -->
        <div class="max-w-2xl mx-auto mt-7">
          <div
            class="flex items-center bg-white rounded-full shadow-xl overflow-hidden relative border border-blue-400"
          >
            <input
              v-model="searchQuery"
              type="text"
              placeholder="What Are You Looking For Today?"
              class="flex-1 px-4 py-3 text-lg outline-none text-center text-gray-700 placeholder:text-gray-400"
              @keyup.enter="handleSearch"
            />
            <button
              v-if="searchQuery"
              @click="clearSearch"
              class="absolute right-10 text-gray-400 hover:text-gray-600 transition px-2"
              title="Clear search"
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
                  d="M6 18L18 6M6 6l12 12"
                />
              </svg>
            </button>
            <button
              @click="handleSearch"
              class="bg-gradient-to-r from-blue-600 to-purple-600 text-white px-4 py-4 hover:from-blue-700 hover:to-purple-700 transition-all font-semibold rounded-full"
            >
              Search Now
            </button>
          </div>
        </div>

        <!-- Rating/Trust indicator -->
        <div
          class="inline-flex items-center justify-center gap-2 mt-8 bg-white/50 backdrop-blur-sm px-4 py-2 rounded-full border border-blue-400"
        >
          <div class="flex text-yellow-400">
            <span>⭐</span>
            <span>⭐</span>
            <span>⭐</span>
            <span>⭐</span>
            <span>⭐</span>
          </div>
          <span class="text-sm text-gray-600 font-medium">915+ 5 Stars</span>
        </div>
      </div>
    </section>

    <!-- Smart Comparison Section -->

    <section class="py-15 mb-3 bg-gradient-to-br from-purple-50 to-pink-50">
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <!-- Left: Text content -->
          <div class="order-2 md:order-1 text-center md:text-left">
            <h2
              class="text-4xl md:text-5xl font-extrabold text-gray-900 mb-6 leading-tight"
            >
              SMART SHOPPING <br />
              WITH <span class="text-pink-600">Online.Com</span>
            </h2>
            <p class="text-lg text-gray-700 mb-8 leading-relaxed">
              MulloKoto lists thousands of products from top Bangladesh
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
          <div class="order-1 md:order-2 flex justify-center">
            <video
              src="./public/videos/shortVideo.mp4"
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
    <section class="py-20 bg-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-4xl font-bold text-center text-gray-900 mb-12">
          BROWSE TOP CATEGORIES
        </h2>

        <!-- Cart Button -->
        <button
          @click="toggleCart"
          class="fixed top-20 right-4 z-50 bg-green-600 text-white p-4 rounded-full shadow-2xl hover:bg-green-700 transition-all"
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
      class="py-20 bg-gradient-to-br from-gray-50 via-purple-50/30 to-pink-50 border-t border-gray-100"
    >
      <div class="max-w-7xl mx-auto px-6 lg:px-8">
        <div class="grid md:grid-cols-2 gap-16 items-center">
          <!-- Left: Video -->
          <div class="flex justify-center relative group">
            <div
              class="absolute -inset-4 bg-purple-200/30 blur-3xl rounded-3xl opacity-50 group-hover:opacity-80 transition duration-500"
            ></div>
            <video
              src="./public/videos/ShortVideo2.mp4"
              autoplay
              muted
              loop
              playsinline
              class="relative z-10 rounded-3xl shadow-5xl w-[290px] max-w-md md:max-w-lg ring-4 ring-yellow-300 group-hover:scale-105 transition-all duration-500"
            ></video>
          </div>

          <!-- Right: Text Content -->
          <div class="text-center md:text-right">
            <h2
              class="text-4xl md:text-5xl font-extrabold text-gray-900 mb-6 leading-snug"
            >
              SMART SHOPPING <br />
              WITH <span class="text-purple-600">Online.Com</span>
            </h2>

            <p class="text-lg text-gray-700 mb-8 leading-relaxed">
              Online.Com lists thousands of products from top Bangladesh
              eCommerce sites like Daraz, Othoba, Pickaboo, Chaldal, AjkerDeal,
              and more. No more worrying about confusing prices across platforms
              — our intelligent comparison algorithm helps you find
              <b>the best deals</b> at <b>the lowest price</b>.
            </p>

            <h4
              class="text-2xl font-semibold bg-gradient-to-r from-purple-600 to-pink-600 text-transparent bg-clip-text"
            >
              Coming Soon..
            </h4>
          </div>
        </div>
      </div>
    </section>

    <!-- 💬 Customer Reviews Section -->
    <section class="py-20 bg-gray-50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Heading -->
        <h2
          class="text-4xl font-bold text-center text-gray-900 mb-14 tracking-wide"
        >
          CUSTOMER REVIEWS
        </h2>

        <!-- Review Cards -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
          <!-- Card 1 -->
          <div
            class="flex flex-col items-center bg-white rounded-2xl p-8 text-center shadow-lg hover:shadow-2xl transition-all duration-300 border border-gray-100"
          >
            <img
              src="/images/images/testi1.jpg"
              alt="Customer 1"
              class="w-20 h-20 rounded-full object-cover ring-4 ring-purple-200 mb-5"
            />
            <h3 class="text-lg font-semibold text-gray-800">Sarah Ahmed</h3>
            <p class="text-gray-600 text-sm mt-2 mb-5 leading-relaxed">
              “Fast delivery and top-quality products! I’m extremely satisfied
              with my shopping experience.”
            </p>
            <div class="flex space-x-1">
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-gray-300 text-lg">★</span>
            </div>
          </div>

          <!-- Card 2 -->
          <div
            class="flex flex-col items-center bg-white rounded-2xl p-8 text-center shadow-lg hover:shadow-2xl transition-all duration-300 border border-gray-100"
          >
            <img
              src="/images/images/testi2.jpg"
              alt="Customer 2"
              class="w-20 h-20 rounded-full object-cover ring-4 ring-purple-200 mb-5"
            />
            <h3 class="text-lg font-semibold text-gray-800">Mahmud Hasan</h3>
            <p class="text-gray-600 text-sm mt-2 mb-5 leading-relaxed">
              “Excellent customer service. They really care about quality and
              customer satisfaction!”
            </p>
            <div class="flex space-x-1">
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
            </div>
          </div>

          <!-- Card 3 -->
          <div
            class="flex flex-col items-center bg-white rounded-2xl p-8 text-center shadow-lg hover:shadow-2xl transition-all duration-300 border border-gray-100"
          >
            <img
              src="/images/images/testi3.jpg"
              alt="Customer 3"
              class="w-20 h-20 rounded-full object-cover ring-4 ring-purple-200 mb-5"
            />
            <h3 class="text-lg font-semibold text-gray-800">Riya Akter</h3>
            <p class="text-gray-600 text-sm mt-2 mb-5 leading-relaxed">
              “I loved how smooth the process was. Everything came exactly as
              described. Highly recommend!”
            </p>
            <div class="flex space-x-1">
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-gray-300 text-lg">★</span>
            </div>
          </div>

          <!-- Card 4 -->
          <div
            class="flex flex-col items-center bg-white rounded-2xl p-8 text-center shadow-lg hover:shadow-2xl transition-all duration-300 border border-gray-100"
          >
            <img
              src="/images/images/ab3.jpg"
              alt="Customer 4"
              class="w-20 h-20 rounded-full object-cover ring-4 ring-purple-200 mb-5"
            />
            <h3 class="text-lg font-semibold text-gray-800">Tanvir Rahman</h3>
            <p class="text-gray-600 text-sm mt-2 mb-5 leading-relaxed">
              “Outstanding product quality! This is now my favorite online
              shopping destination.”
            </p>
            <div class="flex space-x-1">
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-yellow-400 text-lg">★</span>
              <span class="text-gray-300 text-lg">★</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 🎬 Local Video Section -->
    <section class="py-20 bg-white">
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
            class="w-full h-[450px] object-cover transition-transform duration-500 group-hover:scale-105"
          >
            <source src="./public/videos/short.mp4" type="video/mp4" />
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
      class="py-20 bg-gradient-to-br from-purple-600 to-pink-600 text-white"
    >
      <div class="max-w-4xl mx-auto px-4 text-center">
        <h2 class="text-4xl font-bold mb-6">
          GET THE BEST ONLINE <br />
          DEALS ON YOUR INBOX
        </h2>
        <p class="text-xl mb-8">
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
            class="bg-white text-purple-600 px-8 py-4 rounded-lg font-semibold hover:bg-gray-100 transition"
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
    image: "/images/images/s23.jpg",
    store: "Othoba",
    category: "Mobile",
  },
  {
    id: 102,
    name: "Apple iPhone 14 Pro Max",
    price: "165,000",
    image: "/images/images/apple-iphone-14.jpg",
    store: "Ryans",
    category: "Mobile",
  },
  {
    id: 103,
    name: 'MacBook Air M2 13.6" 8GB 256GB',
    price: "125,000",
    image: "/images/images/MacBook Air M2 .jpg",
    store: "Ryans",
    category: "Laptop",
  },
  {
    id: 104,
    name: "Sony WH-1000XM5 Wireless Headphones",
    price: "35,000",
    image: "/images/images/Sony .jpg",
    store: "Othoba",
    category: "Audio",
  },
  {
    id: 105,
    name: "Canon EOS R6 Mark II Mirrorless",
    price: "280,000",
    image: "/images/images/dell-xps g.jpg",
    store: "Ryans",
    category: "Camera",
  },
  {
    id: 106,
    name: 'Samsung 55" 4K Smart TV',
    price: "68,000",
    image: "/images/images/iPad Pro .jpg",
    store: "Othoba",
    category: "TV",
  },
  {
    id: 107,
    name: "Dell XPS 15 9520 Intel Core i7",
    price: "185,000",
    image: "/images/images/dell-xps g.jpg",
    store: "Ryans",
    category: "Laptop",
  },
  {
    id: 108,
    name: 'iPad Pro 12.9" M2 Chip',
    price: "145,000",
    image: "/images/images/iPad Pro .jpg",
    store: "Ryans",
    category: "Tablet",
  },
  {
    id: 109,
    name: "Nikon Z9 Mirrorless Camera",
    price: "520,000",
    image: "/images/images/s23.jpg",
    store: "Ryans",
    category: "Camera",
  },
  {
    id: 110,
    name: 'LG 65" OLED 4K Smart TV',
    price: "195,000",
    image: "/images/images/apple-iphone-14.jpg",
    store: "Othoba",
    category: "TV",
  },
  {
    id: 111,
    name: "Asus ROG Strix Gaming Laptop",
    price: "215,000",
    image: "/images/images/MacBook Air M2 .jpg",
    store: "Ryans",
    category: "Gaming",
  },
  {
    id: 112,
    name: "Apple Watch Series 9 GPS",
    price: "45,000",
    image: "/images/images/Sony .jpg",
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
</style>
