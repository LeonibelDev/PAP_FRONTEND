<template>
  <div id="app">
    
    <link rel="stylesheet" 
        href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" 
        integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" 
        crossorigin="anonymous">

    <router-view></router-view>
  </div>
</template>

<script>
import Login from './components/Login.vue'
import Register from './components/Register.vue'
import Home from './components/Home.vue'
import Product from './components/Product.vue'

export default {
  name: 'App',
  components: {
    Login,
    Home,
    Register,
    Product
  }
}
</script>

<style>

</style>
