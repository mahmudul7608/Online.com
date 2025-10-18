<template>
  <section class="py-20 bg-green-900 from-purple-600 to-pink-600 text-white">
    <div class="max-w-4xl mx-auto px-4 text-center">
      <h2 class="text-4xl font-bold mb-6">
        GET THE BEST ONLINE <br> DEALS ON YOUR INBOX
      </h2>
      <p class="text-xl mb-8">
        Signup Our Newsletter And Receive Periodic Info And Alerts <br>
        On Best Online Deals In Bangladesh
      </p>
      <form @submit.prevent="handleSubmit" class="flex flex-col md:flex-row gap-4 max-w-2xl mx-auto">
        <input 
          v-model="email"
          type="email" 
          placeholder="Input your email here" 
          required
          class="flex-1 px-6 py-4 rounded-lg text-gray-900 outline-none"
        />
        <button type="submit" class="bg-white text-purple-600 px-8 py-4 rounded-lg font-semibold hover:bg-gray-100 transition">
          Submit
        </button>
      </form>
      <p v-if="message" class="mt-4 text-white font-semibold">{{ message }}</p>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const email = ref('')
const message = ref('')

const handleSubmit = () => {
  if (email.value) {
    message.value = 'Thank you for subscribing!'
    email.value = ''
    setTimeout(() => {
      message.value = ''
    }, 3000)
  }
}
</script>
