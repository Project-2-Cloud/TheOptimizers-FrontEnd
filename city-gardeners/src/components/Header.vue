<template>
    <header id="header">
        <img src="logo.png" alt="logo">
        <h2 class="hidden-sm hidden-xs">City Garderers</h2>
        <NavCart />
        <NavLink minor="Gardening" text="Workshops" />
        <NavLink minor="List Of" text="Products" />
        <NavLink minor="Hello, User" text="SignUp/SignIn" />
    </header>
</template>

<script>
import NavLink from "./NavLink"
import NavCart from "./NavCart"

export default {
    name: 'Header',
    components: {
        NavLink,
        NavCart,
    }
}

var lastScrollTop = 0;

$(window).scroll(function () {

var st = $(this).scrollTop();
    if (st < lastScrollTop){
        $('#header').fadeIn();
    } else {
      $('#header').fadeOut();
    }
    lastScrollTop = st;
})
</script>

<style scoped>
header {
    position: fixed;
    height: 10vh;
    background-color: white;
    padding: 1vh 2vw;
    width: 100vw;
    z-index: 10;

}
img {
    height: 8vh;
}
h2 {
    position: relative;
    top: 20%;
    margin-left: 1vw;
    display: inline;
    font-size: 6vh;
    color: green;
}
</style>