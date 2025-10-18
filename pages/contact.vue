<template>
  <div class="min-h-screen bg-white">
    <Header />
    
    <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
      <h1 class="text-4xl font-bold text-gray-900 mb-8">Contact Us</h1>
      
      <form @submit.prevent="handleSubmit" class="space-y-6">
        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Name</label>
          <input 
            v-model="form.name"
            type="text" 
            required
            class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-purple-600 focus:border-transparent"
          />
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Email</label>
          <input 
            v-model="form.email"
            type="email" 
            required
            class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-purple-600 focus:border-transparent"
          />
        </div>

        <div>
          <label class="block text-sm font-medium text-gray-700 mb-2">Message</label>
          <textarea 
            v-model="form.message"
            required
            rows="5"
            class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-purple-600 focus:border-transparent"
          ></textarea>
        </div>

        <button 
          type="submit"
          class="w-full bg-purple-600 text-white py-3 rounded-lg hover:bg-purple-700 transition font-semibold"
        >
          Send Message
        </button>
      </form>

      <p v-if="message" class="mt-4 text-green-600 font-semibold">{{ message }}</p>
    </div>

    <FooterSection />
  </div>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  message: ''
})

const message = ref('')

const handleSubmit = () => {
  message.value = 'Thank you for your message! We will get back to you soon.'
  form.value = { name: '', email: '', message: '' }
  
  setTimeout(() => {
    message.value = ''
  }, 5000)
}
</script>
