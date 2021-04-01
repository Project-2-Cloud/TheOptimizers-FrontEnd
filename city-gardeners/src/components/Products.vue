<template>
    <div id="product" class="container-fluid">
        <h2 id="product-title">Our Products</h2>
        <div id="screen" @click="deselect()" class="container-fluid"></div>
        <div class="row">
            <Item @add-product="addProduct" :id="'product' + item.id" @item-select="selectItem(item.id)" :key="item.id" v-for="item in items" :title="item.title" :price="item.price" :image="item.image" :max="returnMax(item.sellers)" />
        </div>
        <Sellers :sellers="items[lastSelected].sellers" v-if="selected" />
    </div>
</template>

<script>
import Item from "./Item"
import Sellers from "./Sellers"

export default {
    name: 'Products',
    components: {
        Item,
        Sellers,
    },
    data() {
        return {
            items: [],
            lastSelected: null,
            selected: false
        }
    },
    methods: {
        returnMax(sellers) {
            var max = 0
            for(var i = 0; i < sellers.length; ++i) {
                if(sellers[i].quantity > max) {
                    max = sellers[i].quantity
                }
            }
            return max
        },
        addProduct(item) {
            this.$emit('add-product', item)
        },
        selectItem(id) {
            var element = "product"+id
            document.getElementById("screen").style.visibility = "visible"
            document.getElementById(element).setAttribute('id', 'selected')
            this.lastSelected = id;
            this.selected = true
        },
        deselect() {
            document.getElementById("screen").style.visibility = "hidden"
            document.getElementById("selected").setAttribute('id', "product"+this.lastSelected)
            this.selected = false
        }
    },
    created() {
        this.items = [
            {
                id: 0,
                title: "Carrots",
                price: 2.0,
                image: "images/Products/carrot.png",
                sellers: [
                    {
                        id: 0,
                        name: "Rachael",
                        image: "images/Users/3.png",
                        quantity: 10,
                        stars: 4
                    },
                    {
                        id: 1,
                        name: "Mark",
                        image: "images/Users/1.png",
                        quantity: 2,
                        stars: 3
                    },
                    {
                        id: 2,
                        name: "M. Hudson",
                        image: "images/Users/2.png",
                        quantity: 5,
                        stars: 2
                    },
                ]
            },
            {
                id: 1,
                title: "Tomatoes",
                price: 1.5,
                image: "images/Products/tomato.png",
                sellers: [
                    {
                        id: 0,
                        name: "Rachael",
                        image: "images/Users/3.png",
                        quantity: 10,
                        stars: 4
                    },
                    {
                        id: 1,
                        name: "Mark",
                        image: "images/Users/1.png",
                        quantity: 2,
                        stars: 3
                    },
                ]
            },
            {
                id: 2,
                title: "Potatoes",
                price: 1.5,
                image: "images/Products/potato.png",
                sellers: [
                    {
                        id: 0,
                        name: "Rachael",
                        image: "images/Users/3.png",
                        quantity: 10,
                        stars: 4
                    },
                ]
            },
        ]
    },
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
    margin: 10vh 0 0 0;
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