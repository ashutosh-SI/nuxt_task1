<template>
    <div>
      <Navbar />
      <ProductList />
      <Footer />
    </div>
  </template>
  
  <script>
  import Navbar from '~/components/Navbar.vue'
  import Footer from '~/components/Footer.vue'
  import ProductList from '~/components/ProductList.vue'
  
  export default {
    components: {
      Navbar,
      Footer,
      ProductList
    }
  }
  </script>
  