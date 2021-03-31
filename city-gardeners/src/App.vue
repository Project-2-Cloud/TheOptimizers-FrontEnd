<template>
  <Header :key="reRender" :cart="cart" @landing="changePage('landing')" @workshop="changePage('workshop')" @product="changePage('product')" />
  <Landing v-if="page === 'landing'" />
  <WorkShops v-if="page === 'workshop'" @add-workshop="addCart" />
  <Products v-if="page === 'product'" @add-product="addCart" />
  <Footer @landing="changePage('landing')" @workshop="changePage('workshop')" />
</template>

<script>
import Header from "./components/Header"
import Landing from "./components/Landing"
import WorkShops from "./components/WorkShops"
import Products from "./components/Products"
import Footer from "./components/Footer"

export default {
  name: 'App',
  components: {
    Header,
    Landing,
    WorkShops,
    Products,
    Footer
  },
  data() {
    return {
      page: 'landing',
      cart: [],
      reRender: 0
    }
  },
  methods: {
    addCart(item) {
      this.cart = [...this.cart, item]
      console.log(JSON.stringify(this.cart))
      this.reRender += 1
    },
    changePage(change) {
      this.page = change
    }
  }
}
</script>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
html, body {
    height: 100%;
}
.bg {
    opacity: 0.3;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: auto;
    height: 100vh;
}
</style>
