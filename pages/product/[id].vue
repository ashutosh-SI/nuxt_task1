<template>
  <div>
    <Navbar />
    <div v-if="loading">Loading product details...</div>
    <div v-if="error">{{ error }}</div>
    <div v-if="product">
      <ProductDetails :product="product" />
    </div>
    <Footer />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useAsyncData } from '#app'
import Navbar from '~/components/Navbar.vue'
import Footer from '~/components/Footer.vue'
import ProductDetails from '~/components/ProductDetails.vue'
import axios from 'axios'


const route = useRoute()
const productId = route.params.id


const { data: product, error, pending: loading } = await useAsyncData('product', () =>
  axios.get(`https://fakestoreapi.com/products/${productId}`).then(res => res.data)
)
</script>
