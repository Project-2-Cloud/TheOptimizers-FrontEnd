<template>
    <div>
        <img id="cart" src="images/cart.png" alt="cart">
        <p v-if="cartLen > 0">{{ cartLen }}</p>
    </div>
</template>

<script>
export default {
    name: 'NavCart',
    props: {
        cartLen: Number
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
    cursor: pointer;
}
p {
    position: absolute;
    top: 0;
    padding-top: 0.5vh;
    right: -1vh;
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