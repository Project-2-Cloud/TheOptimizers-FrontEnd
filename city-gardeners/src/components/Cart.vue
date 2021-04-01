<template>
    <div id="cart" class="container-fluid">
        <h2>Shopping Cart</h2>
        <div id="empty" v-if="cart.length === 0">
            <h1>The shopping cart is empty. Add some things to your cart.</h1>
        </div>
        <div :key="item.price + Math.random()*100" v-for="item in cart" class="cart-element col-md-8 col-md-push-2 col-xs-12">
            <div class="item" v-if="item.type === 'workshop'">
                <img :src="item.image" alt="item">
                <div class="details">   
                    <h3>{{ item.name }}</h3>
                    <h3 class="price">$ {{ item.price }}</h3>
                    <h4>WorkShop</h4>
                </div>
            </div>
            <div class="item" v-if="item.type === 'product'">
                <img :src="item.image" alt="item">
                <div class="details">
                    <h3>{{ item.name }}</h3>
                    <h3 class="price">$&nbsp;{{ item.price }}</h3>
                    <h4>Product</h4>
                    <h4>{{ item.count }} kg</h4>
                </div>
                <br>
            </div>
        </div>
        <Button id="checkout" text="Checkout" />
    </div>
</template>

<script>
import Button from "./Button"

export default {
    name: 'Cart',
    props: {
        cart: Array
    },
    components: {
        Button
    }
}
</script>

<style scoped>
#cart {
    min-height: 100vh;
}
#empty {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    white-space: nowrap;
}
h2 {
    text-align: center;
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: green;
    font-size: 6vh;
    font-weight: 600;
    margin-top: 15vh;
    margin-bottom: 10vh;
}
.cart-element {
    margin-top: 2vh;
    padding: 2vh;
    background: #DDD;
}
img {
    height: 20vh;
    width: 20vh;
    border-radius: 50%;
}
.details {
    position: absolute;
    left: 15vw;
    display: inline-block;
}
h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 5vh;
    font-weight: 600;
}
.price {
    top: 0;
    left: 40vw;
    position: absolute;
    width: fit-content;
    white-space: nowrap;
}
h4 {
    font-family: 'Montserrat', sans-serif;
    margin-top: 2vh;
    font-size: 2vh;
}
#checkout {
    position: absolute;
    top: 23vh;
    right: 0.5vw;
}
@media only screen and (max-width: 991px) {
    .details {
        left: 30vw;
    }
}
</style>