<template>
  <div class="min-h-screen bg-gradient-to-br from-purple-100 via-purple-200 to-pink-200 pt-16">
    <Header />
    
    <div class="max-w-md mx-auto px-4 py-16">
      <div class="bg-white rounded-2xl shadow-xl p-8">
        <h1 class="text-3xl font-bold text-gray-900 mb-6 text-center">Sign In</h1>
        
        <form class="space-y-4">
          <div>
            <label class="block text-gray-700 font-medium mb-2">Email</label>
            <input 
              type="email" 
              placeholder="Enter your email"
              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
            />
          </div>
          
          <div>
            <label class="block text-gray-700 font-medium mb-2">Password</label>
            <input 
              type="password" 
              placeholder="Enter your password"
              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
            />
          </div>
          
          <button 
            type="submit"
            class="w-full bg-gradient-to-r from-purple-600 to-pink-600 text-white py-3 rounded-lg hover:from-purple-700 hover:to-pink-700 transition font-semibold"
          >
            Sign In
          </button>
        </form>
        
        <p class="text-center mt-6 text-gray-600">
          Don't have an account? 
          <NuxtLink to="/signup" class="text-blue-600 hover:text-blue-700 font-semibold">Sign Up</NuxtLink>
        </p>
      </div>
    </div>
    
    <FooterSection />
  </div>
</template>

<script setup>
// Sign in page
</script>
