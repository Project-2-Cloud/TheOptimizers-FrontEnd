<template>
    <div id="item" class="col-md-4 col-sm-6 col-xs-12">
        <h4 id="item-title">{{ title }}</h4>
        <h4 id="item-price">$ {{ price }}</h4>
        <img @click="$emit('item-select')" :src=image alt="">
        <form id="options">
            <label for="counter">$ {{ price }}&emsp;X&emsp;</label>
            <div class="number-input">
                <button type="button" @click="decreaseCount()" class="minus">-</button>
                <input name="counter" type="number" id="counter" v-model="count">
                <button type="button" @click="increaseCount()" class="plus">+</button>
            </div><br><br>
            <select name="pickup" custom-select mr-sm-2>
                <option value="1">Pickup #1</option>
                <option value="2">Pickup #2</option>
                <option value="3">Pickup #3</option>
                <option value="4">Pickup #4</option>
                <option value="5">Pickup #5</option>
            </select><br><br>
            <input type="date"><br><br>
            <input type="time">
            <AddToCart id="button" :price="price * count" :key="reRender" />
        </form>
    </div>
</template>

<script>
import AddToCart from "./AddToCart"

export default {
    name: 'Item',
    props: {
        title: String,
        price: Number,
        image: String,
    },
    data() {
        return {
            count: 1,
            reRender: 0
        }
    },
    methods: {
        increaseCount() {
            this.count += 1
            this.reRender += 1
        },
        decreaseCount() {
            if (this.count > 1) {
                this.count -= 1
                this.reRender += 1
            }
        }
    },
    components: {
        AddToCart,
    }
}
</script>

<style scoped>
h4 {
    position: absolute;
    font-family: 'Lora', serif;
    color: white;
    font-size: 4vh;
    font-weight: 400;
    text-shadow: 1px 1px 5px black;
}
#item-title {
    top: 20vw;
    left: 4vw;
}
#item-price {
    top: 25vw;
    left: 20vw;
}
img {
    height: 30vw;
    width: 20vw;
    margin-bottom: 5vh;
}
img:hover {
    box-shadow: 0 0 10px white;
}
#options {
    position: relative;
    visibility: hidden;
    top: -60vh;
    left: 0;
}
#options label {
    font-family: 'Lora', serif;
    color: white;
    font-size: 4vh;
    font-weight: 700;
    margin-left: 3vh;
    text-shadow: 1px 1px 5px black;
}
input[type="number"] {
  -webkit-appearance: textfield;
  -moz-appearance: textfield;
  appearance: textfield;
  width: 7vh;
  height: 5vh;
  font-family: 'Montserrat', sans-serif;
  font-size: 4vh;
  font-weight: 700;
  color: white;
  padding-top: 1vh;
  text-align: center;
  border: 0;
  background: none;
}
input[type=number]::-webkit-inner-spin-button, input[type=number]::-webkit-outer-spin-button {
  -webkit-appearance: none;
}
.number-input {
  display: inline-flex;
}
.number-input,
.number-input * {
  box-sizing: border-box;
}
.number-input button {
  background-color: #00B8DE;
  border-radius: 50%;
  width: 5vh;
  border: 0;
  font-size: 4vh;
}
input[type=date], input[type=time] {
    background: transparent;
    background-image: url("data:image/svg+xml;utf8,<svg fill='black' height='24' viewBox='0 0 24 24' width='24' xmlns='http://www.w3.org/2000/svg'><path d='M7 10l5 5 5-5z'/><path d='M0 0h24v24H0z' fill='none'/></svg>");
    background-repeat: no-repeat;
    background-position-x: 100%;
    background-position-y: 5px;
    background-size: 6vh;
    border: 0;
    border-bottom: 5px solid #00B8DE;
    width: 17vw;
    font-family: 'Montserrat', sans-serif;
    text-shadow: 1px 1px 5px black;
    color: white;
    font-size: 4vh;
    font-weight: 700;
    margin-left: 3vh;
}
input[type=time] {
    background: none;
}
#options select {
    -webkit-appearance: none;
    -moz-appearance: none;
    padding: 0;
    background: transparent;
    background-image: url("data:image/svg+xml;utf8,<svg fill='black' height='24' viewBox='0 0 24 24' width='24' xmlns='http://www.w3.org/2000/svg'><path d='M7 10l5 5 5-5z'/><path d='M0 0h24v24H0z' fill='none'/></svg>");
    background-repeat: no-repeat;
    background-position-x: 100%;
    background-position-y: 5px;
    background-size: 6vh;
    border: 0;
    border-bottom: 5px solid #00B8DE;
    width: 17vw;
    font-family: 'Montserrat', sans-serif;
    text-shadow: 1px 1px 5px black;
    color: white;
    font-size: 4vh;
    font-weight: 700;
    margin-left: 3vh;
}
#button {
    position: relative;
    top: 15vh;
}
#selected {
    z-index: 8;
}
#selected #item-price {
    visibility: hidden;
}
#selected #options {
    visibility: visible;
}
@media only screen and (max-width: 991px) {
    img {
        height: 60vw;
        width: 40vw;
    }
    #item-title {
        top: 40vw;
        left: 4vw;
    }
    #item-price {
        top: 50vw;
        left: 30vw;
    }
}
@media only screen and (max-width: 767px) {
    img {
        height: 105vw;
        width: 70vw;
    }
    #item-title {
        top: 70vw;
        left: 4vw;
    }
    #item-price {
        top: 90vw;
        left: 60vw;
    }
}
</style>