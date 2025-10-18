<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-50 via-purple-50 to-pink-50">
    <Header />
    
    <div class="max-w-md mx-auto px-4 py-12">
      <div class="bg-white rounded-2xl shadow-xl p-8">
        <h1 class="text-3xl font-bold text-gray-900 mb-6 text-center">Sign Up</h1>
        
        <form class="space-y-4">
          <div>
            <label class="block text-gray-700 font-medium mb-2">Full Name</label>
            <input 
              type="text" 
              placeholder="Enter your name"
              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
            />
          </div>
          
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
          
          <div>
            <label class="block text-gray-700 font-medium mb-2">Confirm Password</label>
            <input 
              type="password" 
              placeholder="Confirm your password"
              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
            />
          </div>
          
          <button 
            type="submit"
            class="w-full bg-gradient-to-r from-blue-600 to-purple-600 text-white py-3 rounded-lg hover:from-blue-700 hover:to-purple-700 transition font-semibold"
          >
            Sign Up
          </button>
        </form>
        
        <p class="text-center mt-6 text-gray-600">
          Already have an account? 
          <NuxtLink to="/signin" class="text-blue-600 hover:text-blue-700 font-semibold">Sign In</NuxtLink>
        </p>
      </div>
    </div>
    
    <FooterSection />
  </div>
</template>

<script setup>
// Sign up page
</script>
