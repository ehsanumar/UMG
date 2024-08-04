<template>
  <div class="m-6 lg:m-20">
    <div class="text-center">
      <h1 class="text-3xl lg:text-6xl text-gray-800">Popular Picks in Clonto</h1>
      <p class="text-xl lg:text-2xl">
        Cras Pretium Suscipit Tellus Sit Amet Aliquet. Vestib <br />
        Maximus Lacinia Massa Non Porttitor.
      </p>
      <p class="mt-5">
        <span class="text-red-500 flex-wrap"> Specia </span> _________ Newest _________ Featured
        _________ Treading
      </p>
    </div>
    <div class="mt-10 container grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4  p-4">
     <div
  v-for="product in products"
  :key="product.id"
  class="bg-transparent rounded-lg mx-auto w-full overflow-hidden"
  style="height: 400px;" 
>
  <router-link :to="{ name: 'product', params: { id: product.id } }">
    <!-- Product Image -->
    <img :src="product.image" :alt="product.title" class="w-full h-60 object-fill" />
    <!-- Product Details -->
    <div class="p-4 overflow-hidden"> <!-- Ensure the content is hidden if it overflows -->
      <div class="flex justify-between">
         <h2 class="text-lg font-semibold text-gray-800">{{ truncateTitle(product.title) }}</h2>
        <p class="text-gray-500 text-lg mt-1">${{ product.price.toFixed(2) }}</p>
      </div>
      <div class="flex space-x-1 p-2">
        <!-- Use product.image for all thumbnails as a placeholder -->
        <img
          v-for="n in 3"
          :key="n"
          :src="product.image"
          :alt="`Thumbnail ${n}`"
          class="w-12 h-12 rounded shadow cursor-pointer hover:opacity-75"
        />
      </div>
      <!-- Size Options (Static as Example) -->
      <div class="flex space-x-1 my-2">
        <button class="border rounded px-3 py-1 text-sm">S</button>
        <button class="border rounded px-3 py-1 text-sm">M</button>
        <button class="border rounded px-3 py-1 text-sm">L</button>
        <button class="border rounded px-3 py-1 text-sm">XL</button>
      </div>
      <hr />
      <!-- Add to Cart Button -->
      <div class="flex justify-between mt-3">
        <h1 class="text-gray-800 font-semibold cursor-pointer hover:text-blue-600">
          +Add To Cart
        </h1>
        <div class="flex gap-3 text-lg">
          <i
            class="fa-regular fa-heart cursor-pointer hover:text-red-600"
            aria-hidden="true"
          ></i>
          <i
            class="fa-solid fa-rotate cursor-pointer hover:text-blue-600"
            aria-hidden="true"
          ></i>
        </div>
      </div>
    </div>
  </router-link>
</div>

    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      products: [] // Array to hold products
    }
  },
  mounted() {
    this.fetchProducts()
  },
  methods: {
    async fetchProducts() {
      try {
        const response = await axios.get('https://fakestoreapi.com/products/?limit=8')
        this.products = response.data
      } catch (error) {
        console.error('Error fetching products:', error)
      }
    },
    truncateTitle(title) {
      const words = title.split(' ');
      return words.length <= 2 ? title : words.slice(0, 2).join(' ') + '...';
    },

  }
}
</script>
