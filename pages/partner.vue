<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-50 via-purple-50 to-pink-50">
    <Header />
    
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-8 md:py-12">
      <div class="bg-white rounded-2xl shadow-xl p-8 md:p-12">
        <h1 class="text-3xl md:text-4xl font-bold text-gray-900 mb-6">Become a Partner</h1>
        
        <p class="text-lg text-gray-700 mb-8">
          Join Online.com as a partner and reach millions of customers across Bangladesh. 
          Partner with us to grow your business and increase your sales.
        </p>
        
        <div class="grid md:grid-cols-2 gap-8 mb-12">
          <div class="bg-blue-50 p-6 rounded-xl">
            <div class="text-4xl mb-4">🚀</div>
            <h3 class="text-xl font-semibold text-gray-900 mb-2">Grow Your Business</h3>
            <p class="text-gray-700">
              Reach a wider audience and increase your visibility across multiple platforms.
            </p>
          </div>
          
          <div class="bg-purple-50 p-6 rounded-xl">
            <div class="text-4xl mb-4">💰</div>
            <h3 class="text-xl font-semibold text-gray-900 mb-2">Increase Sales</h3>
            <p class="text-gray-700">
              Get more customers and boost your revenue with our smart comparison platform.
            </p>
          </div>
          
          <div class="bg-pink-50 p-6 rounded-xl">
            <div class="text-4xl mb-4">📊</div>
            <h3 class="text-xl font-semibold text-gray-900 mb-2">Analytics & Insights</h3>
            <p class="text-gray-700">
              Access detailed analytics to understand your customers and optimize your offerings.
            </p>
          </div>
          
          <div class="bg-green-50 p-6 rounded-xl">
            <div class="text-4xl mb-4">🤝</div>
            <h3 class="text-xl font-semibold text-gray-900 mb-2">Dedicated Support</h3>
            <p class="text-gray-700">
              Get dedicated support from our team to help you succeed on our platform.
            </p>
          </div>
        </div>
        
        <form class="space-y-4">
          <div class="grid md:grid-cols-2 gap-4">
            <div>
              <label class="block text-gray-700 font-medium mb-2">Business Name</label>
              <input 
                type="text" 
                placeholder="Enter your business name"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
              />
            </div>
            
            <div>
              <label class="block text-gray-700 font-medium mb-2">Contact Person</label>
              <input 
                type="text" 
                placeholder="Enter contact person name"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
              />
            </div>
          </div>
          
          <div class="grid md:grid-cols-2 gap-4">
            <div>
              <label class="block text-gray-700 font-medium mb-2">Email</label>
              <input 
                type="email" 
                placeholder="Enter your email"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
              />
            </div>
            
            <div>
              <label class="block text-gray-700 font-medium mb-2">Phone</label>
              <input 
                type="tel" 
                placeholder="Enter your phone number"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
              />
            </div>
          </div>
          
          <div>
            <label class="block text-gray-700 font-medium mb-2">Message</label>
            <textarea 
              rows="4"
              placeholder="Tell us about your business"
              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500"
            ></textarea>
          </div>
          
          <button 
            type="submit"
            class="w-full bg-gradient-to-r from-blue-600 to-purple-600 text-white py-4 rounded-lg hover:from-blue-700 hover:to-purple-700 transition font-semibold text-lg"
          >
            Submit Partnership Request
          </button>
        </form>
      </div>
    </div>
    
    <FooterSection />
  </div>
</template>

<script setup>
// Partner page
</script>
