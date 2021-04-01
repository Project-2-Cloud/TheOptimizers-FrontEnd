<template>
    <header id="header">
        <div class="navbar-header">
            <img @click="$emit('change', 'landing')" src="logo.png" alt="logo">
            <h2 @click="$emit('change', 'landing')" class="hidden-md hidden-sm hidden-xs">City Garderers</h2>
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#collapsable-nav" aria-expanded="false" id="navbar-button">
                <span class="sr-only">Toggle navigation</span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
            </button>
        </div>
        <div id="collapsable-nav" class="collapsable navbar-collapse collapse">
            <ul id="nav-list" class="nav navbar-nav navbar-right">
              <router-link to="/" tag="li" v-if="!isAuthenticated" class="nav-item" active-class="active">
                <a @click="onLoginClicked" class="navLink nav-link"><NavLink minor="Hello," text="SignUp/Login" /></a>
              </router-link>
              <li v-if="isAuthenticated" class="li-pointer nav-item">
                <div class="dropdown">
                  <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                    {{ getUserName() }}
                  </button>
                  <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
                    <a class="dropdown-item" href="#">Account Settings</a>
                    <a v-if="isPartner" @click="onRegisterClicked" class="dropdown-item" href="#">Register Product</a>
                    <a @click="onLogoutClicked" class="dropdown-item">Logout {{ userEmail }}</a>
                  </div>
                </div>
              </li>
              <li><a class="navLink" @click="$emit('change', 'product')"><NavLink minor="List Of" text="Products" /></a></li>
              <li><a class="navLink" @click="$emit('change', 'workshop')"><NavLink minor="Gardening" text="Workshops" /></a></li>
              <li><a class="navLink" @click="$emit('change', 'customer')"><NavLink minor="Need Help?" text="Support" /></a></li>
              <li><a class="navLink" @click="$emit('change', 'cart')"><NavCart :cartLen="cartLen" /></a></li>
            </ul>
        </div>
    </header>
</template>

<script>
import NavLink from "./NavLink"
import NavCart from "./NavCart"

export default {
  props: {
    cartLen: Number
  },
  components: { 
    NavLink,
    NavCart,
  },
  name: 'NavHeader',
  computed: {
    userEmail() {
      return this.isLoggedIn ? this.currentUser.email : ''
    },
    isAuthenticated() {
      return this.$store.state.user.isAuthenticated;
    },
    isPartner() {
      return this.$store.state.user.partner;
    },
  },
  methods: {
    check() {
      console.log('Check')
    },
    onLoginClicked() {
      window.location = this.$store.state.endpoints.login;
    },
    onLogoutClicked() {
      this.$store.commit("logout");
    },
    onRegisterClicked() {
      let obj = { 'description': 'description', 'id': parseInt("1"), 'price': parseInt("1000"), 'quantity': parseInt("10"), 'thumbnail_url': "thumbnail_url", 'title': "title" }
      this.$store.dispatch("registerProduct", obj);
    },
    getUserName() {
      return this.$store.state.user.name;
    }
  }
}
</script>

<style scoped>
header {
    position: fixed;
    top: 0;
    height: 10vh;
    background-color: white;
    padding: 1vh 2vw;
    width: 100vw;
    z-index: 10;

}
img {
    height: 8vh;
    cursor: pointer;
}
h2 {
    position: absolute;
    top: 2.5vh;
    margin: 0 1vw;
    display: inline;
    font-size: 6vh;
    color: green;
    cursor: pointer;
}
#navbar-button {
    background-color: green;
    height: 6vh;
    width: 6vh;
}
#navbar-button .icon-bar {
    background: white;
    height: 10%;
    width: 100%;
}
ul {
    margin: 0;
    background: white;
}
.navLink {
  text-decoration: none;
  padding: 0px;
}
.navLink:hover {
  background-color: white;
}
</style>