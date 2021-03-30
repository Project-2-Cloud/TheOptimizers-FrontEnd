<template>
    <header id="header">
        <img @click="$emit('landing')" src="logo.png" alt="logo">
        <h2 @click="$emit('landing')" class="hidden-sm hidden-xs">City Garderers</h2>
        <NavCart />
        <NavLink @click="$emit('workshop')" minor="Gardening" text="Workshops" />
        <NavLink minor="List Of" text="Products" />
        <NavLink minor="Hello," text="SignUp/SignIn" />
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
    position: relative;
    top: 20%;
    margin-left: 1vw;
    display: inline;
    font-size: 6vh;
    color: green;
    cursor: pointer;
}
</style>