<template>
    <header id="header">
        <div class="navbar-header">
            <img @click="$emit('landing')" src="logo.png" alt="logo">
            <h2 @click="$emit('landing')" class="hidden-sm hidden-xs">City Garderers</h2>
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#collapsable-nav" aria-expanded="false" id="navbar-button">
                <span class="sr-only">Toggle navigation</span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
            </button>
        </div>
        <div id="collapsable-nav" class="collapsable navbar-collapse collapse">
            <ul id="nav-list" class="nav navbar-nav navbar-right">
                <li><NavLink minor="Hello," text="SignUp/SignIn" /></li>
                <li><NavLink @click="$emit('product')" minor="List Of" text="Products" /></li>
                <li><NavLink @click="$emit('workshop')" minor="Gardening" text="Workshops" /></li>
                <li><NavCart /></li>
            </ul>
        </div>
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
</style>