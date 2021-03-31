<template>
    <input type="submit" :value="'$ '+price+', Add to Cart'">
</template>

<script>
export default {
    name: 'AddToCart',
    props: {
        price: Number,
    }
}
</script>

<style scoped>
input {
    background: #00B8DE;
    width: 30vh;
    height: 6vh;
    border-radius: 3vh;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: white;
    font-size: 2.5vh;
    font-weight: 700;
}
</style>