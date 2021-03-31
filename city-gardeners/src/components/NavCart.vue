<template>
    <img id="cart" src="images/cart.png" alt="cart">
    <p v-if="cart.length > 0">{{ cart.length }}</p>
</template>

<script>
export default {
    name: 'NavCart',
    props: {
        cart: Array
    },
    data() {
        return {
            len: 0
        }
    }
}
</script>

<style scoped>
#cart {
    height: 6vh;
    margin-top: 1vh;
    margin-left: 2.5vw;
}
p {
    position: absolute;
    top: 0;
    left: 10vh;
    border-radius: 50%;
    background-color: red;
    height: 3vh;
    width: 3vh;
    font-family: 'Montserrat', sans-serif;
    font-size: 2.3vh;
    font-weight: 600;
    text-align: center;
}
</style>