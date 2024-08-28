<template>
    <div class="product-details">
      <img :src="product.image" alt="Product image" />
      <h2>{{ product.title }}</h2>
      <p>{{ product.description }}</p>
      <p><strong>Category:</strong> {{ product.category }}</p>
      <p><strong>Price:</strong> ${{ product.price }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      product: {
        type: Object,
        required: true
      }
    }
  }
  </script>
  
  <style>
  .product-details {
    max-width: 600px;
    margin: auto;
    text-align: center;
  }
  .product-details img {
    max-width: 100%;
    height: auto;
  }
  </style>
  