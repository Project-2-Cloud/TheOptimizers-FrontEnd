<template>
    <div id="seller">
        <div class="seller-info" :key="seller.id" v-for="seller in sellers" :id="'seller'+seller.id" @click="selectSeller(seller.id)">
            <img :src="seller.image" alt="seller">
            <section>
                <h2>{{ seller.name }}</h2>
                <h4>{{ seller.quantity }} kg</h4>
                <p>{{ seller.stars }}</p>
            </section>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Sellers',
    props: {
        sellers: Array
    },
    data() {
        return {
            lastselected: 'seller0'
        }
    },
    methods: {
        selectSeller(id) {
            document.getElementById(this.lastselected).style.opacity = "0.7"
            var element = 'seller' + id
            document.getElementById(element).style.opacity = "1"
            this.lastselected = element
        },
    },
}
</script>

<style scoped>
#seller {
    position: fixed;
    bottom: 0;
    left: 0;
    z-index: 9;
}
.seller-info {
    display: inline-flex;
    background: #AFAFAF;
    border-radius: 10px;
    padding: 1vh;
    margin-left: 10vh;
    opacity: 0.7;
}
#seller0 {
    opacity: 1;
}
img {
    border-radius: 50%;
    height: 15vh;
}
section {
    display: inline-block;
    margin: 0 2vh;
    color: white;
}
h2 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 4vh;
}
h4 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 2vh;
}
</style>