<template>
    <div id="product" class="container-fluid">
        <h2 id="product-title">Our Products</h2>
        <div class="row">
            <Item title="Carrots" price="2.0" image="images/Products/carrot.png" />
            <Item title="Tomatoes" price="1.5" image="images/Products/tomato.png" />
            <Item title="Potatoes" price="1.5" image="images/Products/potato.png" />
        </div>
    </div>
</template>

<script>
import Item from "./Item"

export default {
    name: 'Products',
    components: {
        Item,
    }
}
</script>

<style scoped>
#product {
    background: black;
}
#product-title {
    text-align: center;
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: lightgreen;
    font-size: 6vh;
    font-weight: 600;
    margin-top: 15vh;
}
.row {
    margin: 10vh 0;
    text-align: center;
}
</style>