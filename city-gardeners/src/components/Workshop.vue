<template>
    <form @submit="onSubmit" id="workshop" class="col-md-4 col-sm-6 col-xs-12">
        <h4>{{ title }} <span id="workshop-price">$ {{ price }}</span></h4>
        <img @click="$emit('workshop-select')" :src=image alt="">
        <AddToCart id="button" :price="price" />
    </form>    
</template>

<script>
import AddToCart from "./AddToCart"

export default {
    name: 'Workshop',
    props: {
        title: String,
        price: Number,
        image: String,
    },
    components: {
        AddToCart,
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()
            const newProduct = {
                type: "workshop",
                image: this.image,
                name: this.title,
                price: this.price,
            }

            this.$emit('add-workshop', newProduct)
        }
    }
}
</script>

<style scoped>
#workshop {
    text-align: left;
}
#workshop h4 {
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: green;
    font-size: 3vh;
    font-weight: 600;
    text-align: left;
    margin-left: 4vh;
}
#workshop-price {
    float: right;
    margin-right: 4vh;
}
#workshop img {
    height: 20vw;
    width: 20vw;
    margin-bottom: 5vh;
}
#workshop img:hover {
    box-shadow: 0 0 10px black;
}
#selected {
    z-index: 7;
}
#selected h4 {
    color: lightgreen;
}
#selected #button {
    visibility: visible;
}
#button {
    visibility: hidden;
    position: relative;
    top: -15vh;
}
@media only screen and (max-width: 991px) {
    #workshop img {
        height: 35vw;
        width: 35vw;
    }
}
@media only screen and (max-width: 767px) {
    #workshop img {
        height: 70vw;
        width: 70vw;
    }
}
</style>