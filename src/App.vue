<template>
  <div id="app">
    <ProductList/>
  </div>
</template>

<script>
import ProductList from './components/ProductList.vue'
import '@/assets/css/style.scss'

export default {
  name: 'App',
  components: {
    ProductList
  }
}
</script>

<style lang="scss">
#app {
  font-family: Arial, "Nimbus Sans L", Helvetica, sans-serif;;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
