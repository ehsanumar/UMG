<template>
  <div class="   m-6 lg:m-20 justify-center">
    <div class="text-center">
      <h1 class="text-3xl lg:text-6xl text-gray-800">Daily Flash Sale!</h1>
      <p class="text-xl lg:text-2xl">
        Cras Pretium Suscipit Tellus Sit Amet Aliquet. Vestib <br />
        Maximus Lacinia Massa Non Porttitor.
      </p>
    </div>
  <div class=" mt-10 container grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3">
  <!-- Map over the products -->
  <div
    v-for="product in products"
    :key="product.id"
    class="bg-transparent rounded-lg mx-auto overflow-hidden w-full"
  >
    <router-link :to="{ name: 'product', params: { id: product.id } }">
      <!-- Product Card with Fixed Height -->
      <div class="bg-white shadow-lg rounded-lg overflow-hidden h-full flex flex-col">
        <!-- Product Image -->
        <img :src="product.image" :alt="product.title" class="w-full h-60 object-fill" />
        <!-- Product Details -->
        <div class="p-4 flex flex-col flex-grow">
          <div class="flex justify-between mb-4">
            <h2 class="text-lg font-semibold text-gray-800 ">{{ product.title }}</h2>
            <p class="text-gray-500 text-lg">${{ product.price.toFixed(2) }}</p>
          </div>
          <!-- Thumbnails -->
          <div class="flex space-x-1 p-2 mb-4">
            <img
              v-for="n in 3"
              :key="n"
              :src="product.image"
              :alt="`Thumbnail ${n}`"
              class="w-12 h-12 rounded shadow cursor-pointer hover:opacity-75"
            />
          </div>
          <!-- Size Options -->
          <div class="flex space-x-1 mb-4">
            <button class="border rounded px-3 py-1 text-sm">S</button>
            <button class="border rounded px-3 py-1 text-sm">M</button>
            <button class="border rounded px-3 py-1 text-sm">L</button>
            <button class="border rounded px-3 py-1 text-sm">XL</button>
          </div>
          <hr />
          <!-- Add to Cart Button -->
          <div class="flex justify-between mt-3 items-end">
            <h1 class="text-gray-800 font-semibold cursor-pointer hover:text-blue-600">
              + Add To Cart
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
      </div>
    </router-link>
  </div>
</div>

    <div class="container mx-auto p-4">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
        <!-- Left Column -->
        <div class="grid grid-rows-2 gap-4">
          <!-- Modern -->
          <div class="relative">
            <img
              src="https://via.placeholder.com/300x300"
              alt="Modern"
              class="w-full h-full object-cover"
            />
            <div class="absolute bottom-1 left-2">
              <p class="text-black text-2xl font-bold">MODERN</p>
            </div>
          </div>

          <!-- Newest -->
          <div class="relative">
            <img
              src="https://via.placeholder.com/300x300"
              alt="Newest"
              class="w-full h-full object-cover"
            />
            <div class="absolute bottom-1 left-2">
              <p class="text-black text-2xl font-bold">NEWEST</p>
            </div>
          </div>
        </div>

        <!-- Center Column -->
        <div class="relative row-span-2">
          <!-- 25% OFF -->
          <img
            src="https://via.placeholder.com/600x600"
            alt="25% OFF"
            class="w-full h-full object-cover"
          />
          <div
            class="absolute inset-0 flex flex-col items-center justify-between p-5 bg-black bg-opacity-25"
          >
            <div class="block">
              <p class="text-white text-3xl font-bold">25% OFF</p>
              <p class="text-white text-xl">All Modern Collections</p>
            </div>
            <h1 class="text-white underline text-3xl mt-5 bottom-2">
              <span class="bg-rose-500">Sh</span>op Now
              <i class="fa-solid fa-arrow-right-long ml-3" aria-hidden="true"></i>
            </h1>
          </div>
        </div>

        <!-- Right Column -->
        <div class="grid grid-rows-2 gap-4">
          <!-- Modern -->
          <div class="relative">
            <img
              src="https://via.placeholder.com/300x300"
              alt="Modern"
              class="w-full h-full object-cover"
            />
            <div class="absolute bottom-1 left-2">
              <p class="text-black text-2xl font-bold">MODERN</p>
            </div>
          </div>

          <!-- Newest -->
          <div class="relative">
            <img
              src="https://via.placeholder.com/300x300"
              alt="Newest"
              class="w-full h-full object-cover"
            />
            <div class="absolute bottom-1 left-2">
              <p class="text-black text-2xl font-bold">NEWEST</p>
            </div>
          </div>
        </div>
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
        const response = await axios.get('https://fakestoreapi.com/products/?limit=3')
        this.products = response.data
      } catch (error) {
        console.error('Error fetching products:', error)
      }
    }
  }
}
</script>
