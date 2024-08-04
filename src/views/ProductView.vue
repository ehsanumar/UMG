<template>
  <div class="product-detail container mx-auto p-4">
    <div v-if="product" class="product-info">
      <h1 class="text-3xl font-bold text-gray-800 mb-4">{{ product.title }}</h1>
      <img :src="product.image" :alt="product.title" class="w-64 h-64 object-cover mb-4" />
      <p class="text-xl text-gray-700">{{ product.description }}</p>
      <p class="text-gray-500 mt-2">Category: {{ product.category }}</p>
      <p class="text-xl font-semibold text-gray-800 mt-2">Price: ${{ product.price.toFixed(2) }}</p>
      <div class="flex items-center mt-2">
        <div class="flex text-yellow-400">
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
        <p class="text-gray-600 ml-2">({{ product.rating.count }} reviews)</p>
      </div>
    </div>
    <div v-else>
      <p>Loading product data...</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      product: null
    }
  },
  async created() {
    await this.fetchProduct()
  },
  watch: {
    '$route.params.id': 'fetchProduct'
  },
  methods: {
    async fetchProduct() {
      const productId = this.$route.params.id
      try {
        const response = await axios.get(`https://fakestoreapi.com/products/${productId}`)
        this.product = response.data
      } catch (error) {
        console.error('Error fetching product:', error)
      }
    }
  }
}
</script>

<style scoped>
.product-detail {
  max-width: 600px;
}
</style>
