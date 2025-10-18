<template>
  <section class="py-16 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-4xl font-bold text-center text-gray-900 mb-12">TESTIMONIALS</h2>
      
      <div class="grid md:grid-cols-3 gap-8">
        <div v-for="testimonial in testimonials" :key="testimonial.name" class="bg-gray-50 rounded-lg p-8 hover:shadow-xl transition">
          <p class="text-gray-700 mb-6 italic">"{{ testimonial.text }}"</p>
          <div class="flex items-center">
            <img :src="testimonial.image" :alt="testimonial.name" class="w-16 h-16 rounded-full mr-4 object-cover" />
            <div>
              <h4 class="font-bold text-gray-900">{{ testimonial.name }}</h4>
              <p class="text-gray-600 text-sm">{{ testimonial.role }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const testimonials = [
  {
    name: 'SAIFUL AZAD',
    role: 'Cloud Engineer',
    image: 'https://mullokoto.com/image/saiful.jpg',
    text: 'In the context of Bangladesh, finding a suitable product at reasonable pricing is challenging. Being informed about pricing of the same product in different merchants leverages customer satisfaction and negotiation to impact personal finance positively. Online.com satisfies those demands. Now, before purchasing, I can motivate myself to deal the best.'
  },
  {
    name: 'NAZMUS SAKIB',
    role: 'Entrepreneur',
    image: 'https://mullokoto.com/image/sakib.jpg',
    text: 'As we don\'t have Amazon or Walmart it\'s hard to find better deals. Then I came across Online.com, where thousands of products are listed on multiple e-commerce sites. Here I can search and sort products and compare what I want to buy, they even added a wish list option. I am reassured that the best deal is a search away.'
  },
  {
    name: 'POLASH AHMAD',
    role: 'Software Developer',
    image: 'https://mullokoto.com/image/polash.jpg',
    text: 'In the context of Bangladesh, finding a suitable product at reasonable pricing is challenging. Being informed about pricing of the same product in different merchants leverages customer satisfaction and negotiation to impact personal finance positively. Online.com satisfies those demands. Now, before purchasing, I can motivate myself to get the best deal.'
  }
]
</script>
