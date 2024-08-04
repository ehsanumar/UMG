<template>
  <div class="container mx-auto p-4 mb-20">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 m-4">
      <div
      v-for="product in products"
      :key="product.id"
      class="block p-4 text-center items-center justify-center"
      >
      <p class="text-gray-700 text-2xl mb-4 text-left">Hot Product</p>
      <router-link :to="{ name: 'product', params: { id: product.id } }">
        <div class="flex gap-4 items-center">
          <img
            :src="product.image"
            :alt="product.title"
            class="w-24 h-32 object-cover rounded-lg"
          />
          <div class="block flex-grow items-center text-center">
            <p class="text-gray-700 font-semibold">{{ truncateTitle(product.title) }}</p>
            <p class="text-gray-500">{{ product.category }}</p>
            <div class="flex text-yellow-500  text-center">
              <!-- Use product's rating for stars -->
              <i
                v-for="n in Math.floor(product.rating.rate)"
                :key="n"
                class="fa-solid fa-star"
                aria-hidden="true"
              ></i>
              <i
                v-if="product.rating.rate % 1 !== 0"
                class="fa-regular fa-star-half-stroke"
                aria-hidden="true"
              ></i>
              <i
                v-for="n in 5 - Math.ceil(product.rating.rate)"
                :key="'empty-' + n"
                class="fa-regular fa-star"
                aria-hidden="true"
              ></i>
            </div>
            <p class="text-gray-900 text-xl font-bold">${{ product.price.toFixed(2) }}</p>
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
        const response = await axios.get('https://fakestoreapi.com/products/?limit=12')
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
