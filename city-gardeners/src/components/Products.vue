<template>
    <div id="product" class="container-fluid">
        <h2 id="product-title">Our Products</h2>
        <div id="screen" @click="deselect()" class="container-fluid"></div>
        <div class="row">
            <Item :id="'product' + item.id" @item-select="selectItem(item.id)" :key="item.id" v-for="item in items" :title="item.title" :price="item.price" :image="item.image" />
        </div>
    </div>
</template>

<script>
import Item from "./Item"

export default {
    name: 'Products',
    components: {
        Item,
    },
    data() {
        return {
            items: []
        }
    },
    created() {
        this.items = [
            {
                id: 0,
                title: "Carrots",
                price: 2.0,
                image: "images/Products/carrot.png",
            },
            {
                id: 1,
                title: "Tomatoes",
                price: 1.5,
                image: "images/Products/tomato.png",
            },
            {
                id: 2,
                title: "Potatoes",
                price: 1.5,
                image: "images/Products/potato.png",
            },
        ]
    },
    methods: {
        selectItem(id) {
            var element = "product"+id
            document.getElementById("screen").style.visibility = "visible"
            document.getElementById(element).setAttribute('id', 'selected')
            this.lastSelected = id;
        },
        deselect() {
            document.getElementById("screen").style.visibility = "hidden"
            document.getElementById("selected").setAttribute('id', "product"+this.lastSelected)
        }
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
#screen {
    position: fixed;
    top:0;
    left:0;
    height: 100vh;
    width: 100%;
    z-index: 5;
    visibility: hidden;
    opacity: 0.5;
    background: black;
}
</style>