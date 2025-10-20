<template>
  <div
    class="min-h-screen bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200 pt-16"
  >
    <Header />

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
                :alt="item.title"
                class="w-20 h-20 object-cover rounded"
              />
              <div class="flex-1">
                <h3 class="font-semibold text-sm">{{ item.title }}</h3>
                <p class="text-blue-600 font-bold">
                  ${{ item.price.toFixed(2) }}
                </p>
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
                  >${{ cartSubtotal.toFixed(2) }}</span
                >
              </div>
              <div class="flex justify-between text-gray-700">
                <span>VAT (15%):</span>
                <span class="font-semibold">${{ cartVAT.toFixed(2) }}</span>
              </div>
              <div
                class="flex justify-between text-xl font-bold text-gray-900 border-t pt-3"
              >
                <span>Total:</span>
                <span class="text-blue-600">${{ cartTotal.toFixed(2) }}</span>
              </div>
              <button
                class="w-full bg-gradient-to-r from-blue-600 to-purple-600 text-white py-4 rounded-xl hover:from-blue-700 hover:to-purple-700 transition-all font-semibold text-lg mt-4"
              >
                Checkout
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 md:py-12">

      <!-- Search Header -->
      <div class="mb-8">
        <h1 class="text-3xl md:text-4xl font-bold text-gray-900 mb-6 text-center">
          {{ searchTitle }}
        </h1>

        <!-- Search Input -->
        <div class="max-w-2xl mx-auto" ref="searchInputRef">
          <div
            class="flex items-center bg-white border-2 border-purple-300 rounded-full shadow-2xl overflow-hidden hover:border-purple-400 transition-all"
          >
            <input
              v-model="searchQuery"
              type="text"
              placeholder="Search for products..."
              class="flex-1 px-6 py-3 text-sm outline-none text-center text-gray-700 placeholder:text-gray-500 font-medium"
              @keyup.enter="handleSearch"
            />
            <button
              @click="handleSearch"
              class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-6 py-3 hover:from-purple-700 hover:to-pink-700 transition-all font-bold text-sm rounded-full shadow-lg"
            >
              Search
            </button>
          </div>
        </div>
      </div>

      <!-- Category Filters -->
      <div class="mb-8 flex flex-wrap gap-3">
        <button
          v-for="cat in categories"
          :key="cat.value"
          @click="filterByCategory(cat.value)"
          :class="[
            'px-4 py-2 rounded-full font-medium transition-all duration-300 shadow-md hover:shadow-lg',
            selectedCategory === cat.value
              ? 'bg-blue-600 text-white'
              : 'bg-white text-gray-700 hover:bg-blue-50',
          ]"
        >
          {{ cat.label }}
        </button>
      </div>

      <!-- Loading State -->
      <div v-if="loading" class="flex justify-center items-center py-20">
        <div
          class="animate-spin rounded-full h-16 w-16 border-t-4 border-b-4 border-blue-600"
        ></div>
      </div>

      <!-- Error State -->
      <div v-else-if="error" class="text-center py-20">
        <div class="text-red-600 text-xl mb-4">⚠️ Error loading products</div>
        <p class="text-gray-600">{{ error }}</p>
        <button
          @click="fetchProducts"
          class="mt-4 px-6 py-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition"
        >
          Try Again
        </button>
      </div>

      <!-- No Results -->
      <div
        v-else-if="!loading && filteredProducts.length === 0"
        class="text-center py-20"
      >
        <div class="text-gray-400 text-6xl mb-4">🔍</div>
        <h2 class="text-2xl font-semibold text-gray-700 mb-2">
          No products found
        </h2>
        <p class="text-gray-600">Try a different search term or category</p>
      </div>

      <!-- Product Grid -->
      <div
        v-else
        class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6"
      >
        <div
          v-for="product in filteredProducts"
          :key="product.id"
          class="bg-white rounded-2xl shadow-lg overflow-hidden hover:shadow-2xl transition-all duration-300 hover:-translate-y-2 group"
        >
          <!-- Product Image -->
          <div
            class="relative h-64 bg-gray-100 flex items-center justify-center p-4 overflow-hidden cursor-pointer"
            @click="goToProduct(product.id)"
          >
            <img
              :src="product.thumbnail"
              :alt="product.title"
              class="max-h-full max-w-full object-contain group-hover:scale-110 transition-transform duration-300"
            />
            <div
              class="absolute top-3 right-3 bg-blue-600 text-white px-3 py-1 rounded-full text-xs font-semibold"
            >
              {{ product.category }}
            </div>
            <div
              class="absolute top-3 left-3 bg-green-600 text-white px-3 py-1 rounded-full text-xs font-semibold"
            >
              -{{ product.discountPercentage }}%
            </div>
          </div>

          <!-- Product Info -->
          <div class="p-4">
            <h3
              class="text-lg font-semibold text-gray-900 mb-2 line-clamp-2 group-hover:text-blue-600 transition cursor-pointer"
              @click="goToProduct(product.id)"
            >
              {{ product.title }}
            </h3>
            <p class="text-gray-600 text-sm mb-3 line-clamp-2">
              {{ product.description }}
            </p>

            <!-- Rating -->
            <div class="flex items-center mb-3">
              <div class="flex items-center text-yellow-500 mr-2">
                <span class="mr-1">⭐</span>
                <span class="text-sm font-semibold">{{
                  product.rating || 0
                }}</span>
              </div>
              <span class="text-gray-500 text-xs"
                >({{ product.stock }} in stock)</span
              >
            </div>

            <!-- Price -->
            <div class="flex items-center justify-between mb-3">
              <span class="text-2xl font-bold text-blue-600"
                >${{ product.price }}</span
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

      <!-- Results Count -->
      <div
        v-if="!loading && filteredProducts.length > 0"
        class="mt-8 text-center text-gray-600"
      >
        Showing {{ filteredProducts.length }} products
      </div>
    </div>

    <FooterSection />
  </div>
</template>

<script setup>
import { ref, computed, onMounted, watch } from "vue";
import { useRoute, useRouter } from "vue-router";

const route = useRoute();
const router = useRouter();

const searchQuery = ref("");
const products = ref([]);
const loading = ref(true);
const error = ref(null);
const selectedCategory = ref("all");
const cart = ref([]);
const showCart = ref(false);
const searchInputRef = ref(null);

const categories = ref([{ label: "All Products", value: "all" }]);

const VAT_RATE = 0.15; // 15% VAT

const searchTitle = computed(() => {
  if (route.query.category) {
    const cat = categories.value.find((c) => c.value === route.query.category);
    return cat ? `${cat.label}` : "Search Results";
  }
  if (route.query.q) {
    return `Search Results for "${route.query.q}"`;
  }
  return "All Products";
});

const filteredProducts = computed(() => {
  return products.value;
});

const cartSubtotal = computed(() => {
  return cart.value.reduce((sum, item) => sum + item.price * item.quantity, 0);
});

const cartVAT = computed(() => {
  return cartSubtotal.value * VAT_RATE;
});

const cartTotal = computed(() => {
  return cartSubtotal.value + cartVAT.value;
});

const cartItemCount = computed(() => {
  return cart.value.reduce((sum, item) => sum + item.quantity, 0);
});

const fetchProducts = async () => {
  try {
    loading.value = true;
    error.value = null;

    let url = "https://dummyjson.com/products";

    // If there's a search query, use the search endpoint
    if (route.query.q) {
      url = `https://dummyjson.com/products/search?q=${encodeURIComponent(
        route.query.q
      )}`;
    }

    const response = await fetch(url);

    if (!response.ok) {
      throw new Error("Failed to fetch products");
    }

    const data = await response.json();
    products.value = data.products || [];

    // Extract unique categories
    const uniqueCategories = [
      ...new Set(products.value.map((p) => p.category)),
    ];
    categories.value = [
      { label: "All Products", value: "all" },
      ...uniqueCategories.map((cat) => ({
        label: cat.charAt(0).toUpperCase() + cat.slice(1),
        value: cat,
      })),
    ];
  } catch (err) {
    error.value = err.message;
    console.error("Error fetching products:", err);
  } finally {
    loading.value = false;
  }
};

const handleSearch = () => {
  if (searchQuery.value.trim()) {
    router.push(`/search?q=${encodeURIComponent(searchQuery.value)}`);
  } else {
    router.push("/search");
  }
};

const filterByCategory = async (category) => {
  selectedCategory.value = category;

  if (category === "all") {
    await fetchProducts();
  } else {
    try {
      loading.value = true;
      const response = await fetch(
        `https://dummyjson.com/products/category/${encodeURIComponent(
          category
        )}`
      );
      const data = await response.json();
      products.value = data.products || [];
    } catch (err) {
      error.value = err.message;
    } finally {
      loading.value = false;
    }
  }
};

const goToProduct = (id) => {
  router.push(`/product/${id}`);
};

const addToCart = (product) => {
  const existingItem = cart.value.find((item) => item.id === product.id);

  if (existingItem) {
    existingItem.quantity++;
  } else {
    cart.value.push({
      id: product.id,
      title: product.title,
      price: product.price,
      image: product.thumbnail,
      quantity: 1,
    });
  }

  showCart.value = true;
  setTimeout(() => {
    showCart.value = false;
  }, 3000);
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

const scrollToSearch = () => {
  if (searchInputRef.value) {
    searchInputRef.value.scrollIntoView({ behavior: 'smooth', block: 'center' });
  }
};

// Watch route changes
watch(
  () => route.query,
  (newQuery) => {
    if (newQuery.q) {
      searchQuery.value = newQuery.q;
    }
    fetchProducts();
  },
  { immediate: false }
);

onMounted(() => {
  if (route.query.q) {
    searchQuery.value = route.query.q;
  }
  fetchProducts();
});
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
