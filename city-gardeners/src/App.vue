<template>
  <Header @landing="changePage('landing')" @workshop="changePage('workshop')" />
  <Landing v-if="page === 'landing'" />
  <WorkShops v-if="page === 'workshop'" />
  <Footer @landing="changePage('landing')" @workshop="changePage('workshop')" />
</template>

<script>
import Header from "./components/Header"
import Landing from "./components/Landing"
import WorkShops from "./components/WorkShops"
import Footer from "./components/Footer"

export default {
  name: 'App',
  components: {
    Header,
    Landing,
    WorkShops,
    Footer
  },
  data() {
    return {
      page: 'landing'
    }
  },
  methods: {
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
