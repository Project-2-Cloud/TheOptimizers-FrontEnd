<template>
    <footer class="container-fluid">
        <div class="row">
            <div class="col col-md-3 col-sm-6 col-xs-12">
                <div>
                    <h2>Navigate</h2>
                    <p @click="$emit('change', 'product')">&#8226; View Products</p>
                    <p @click="$emit('change', 'workshop')">&#8226; Gardening Workshops</p>
                    <p @click="$emit('change', 'customer')">&#8226; Customer Self</p>
                    <p @click="$emit('change', 'cart')">&#8226; Checkout</p>
                </div>
            </div>
            <div class="col col-md-3 col-sm-6 col-xs-12">
                <div>
                    <h2>Partners</h2>
                    <p>&#8226; Partner 1</p>
                    <p>&#8226; Partner 2</p>
                    <p>&#8226; Partner 3</p>
                    <p>&#8226; Partner 4</p>
                    <p>&#8226; Partner 5</p>
                </div>
            </div>
            <div class="col col-md-3 col-sm-6 col-xs-12">
                <div>
                    <h2>Sponsors</h2>
                    <p>&#8226; Sponsor 1</p>
                    <p>&#8226; Sponsor 2</p>
                    <p>&#8226; Sponsor 3</p>
                    <p>&#8226; Sponsor 4</p>
                </div>
            </div>
            <div class="col col-md-3 col-sm-6 col-xs-12">
                <div>
                    <h2>Socials</h2>
                    <p>&#8226; Instagram</p>
                    <p>&#8226; Facebook</p>
                    <p>&#8226; Twitter</p>
                    <p>&#8226; Linked In</p>
                </div>
            </div>
        </div>
        <h4>&copy; The Optimisers, 2021</h4>
    </footer>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style scoped>
footer {
    background-color: #555;
}
.col div {
    margin: 3vh auto;
    width: fit-content;
    text-align: left;
}
h2 {
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: white;
    font-size: 2vw;
    font-weight: 600;
}
p {
    font-family: 'Lora', sans-serif;
    color: white;
    font-size: 1vw;
    font-weight: 400;
    margin-left: 1vw;
    cursor: pointer;
}
h4 {
    font-family: 'Lora', sans-serif;
    font-size: 1vw;
    font-weight: 600;
    color: white;
    text-align: center;
}
@media only screen and (max-width: 991px) {
    h2 {
        font-size: 5vw;
    }
    p {
        font-size: 2.1vw;
    }
    h4 {
        font-size: 3vw;
    }
}
@media only screen and (max-width: 575px) {
    p {
        font-size: 3vw;
    }
}
</style>