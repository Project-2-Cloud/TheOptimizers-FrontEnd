<template>
    <div id="item" class="col-md-4 col-sm-6 col-xs-12">
        <h4 id="item-title">{{ title }}</h4>
        <h4 id="item-price">$ {{ price }}</h4>
        <img :src=image alt="">
    </div>
</template>

<script>
export default {
    name: 'Item',
    props: {
        title: String,
        price: Number,
        image: String,
    }
}
</script>

<style scoped>
#item h4 {
    position: absolute;
    font-family: 'Lora', serif;
    color: white;
    font-size: 4vh;
    font-weight: 400;
    text-shadow: 1px 1px 2px black;
}
#item #item-title {
    top: 20vw;
    left: 4vw;
}
#item #item-price {
    top: 25vw;
    left: 20vw;
}
#item img {
    height: 30vw;
    width: 20vw;
    margin-bottom: 5vh;
}
@media only screen and (max-width: 991px) {
    #item img {
        height: 60vw;
        width: 40vw;
    }
    #item #item-title {
        top: 40vw;
        left: 4vw;
    }
    #item #item-price {
        top: 50vw;
        left: 30vw;
    }
}
@media only screen and (max-width: 767px) {
    #item img {
        height: 105vw;
        width: 70vw;
    }
    #item #item-title {
        top: 70vw;
        left: 4vw;
    }
    #item #item-price {
        top: 90vw;
        left: 60vw;
    }
}
</style>