<template>
    <div>
      <h2>Product List</h2>
      <div v-if="loading">Loading products...</div>
      <div v-if="error">{{ error }}</div>
      <div v-if="products.length">
        <div v-for="product in products" :key="product.id">
          <ProductCard :product="product" />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios'
  import ProductCard from '~/components/ProductCard.vue'
  
  export default {
    components: {
      ProductCard
    },
    data() {
      return {
        products: [],
        loading: true,
        error: null
      }
    },
    async created() {
      try {
        const response = await axios.get('https://fakestoreapi.com/products')
        this.products = response.data
      } catch (err) {
        this.error = 'Failed to load products'
      } finally {
        this.loading = false
      }
    }
  }
  </script>
  