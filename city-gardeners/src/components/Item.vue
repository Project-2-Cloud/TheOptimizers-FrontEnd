<template>
    <div class="col-md-4 col-sm-6 col-xs-12">
        <h4 id="item-title">{{ title }}</h4>
        <h4 id="item-price">$ {{ price }}</h4>
        <img @click="$emit('item-select')" :src=image alt="">
        <form @submit="onSubmit" id="options">
            <label for="counter">$ {{ price }}&emsp;X&emsp;</label>
            <div class="number-input">
                <button type="button" @click="decreaseCount()" class="minus">-</button>
                <input name="counter" type="number" id="counter" v-model="count">
                <button type="button" @click="increaseCount()" class="plus">+</button>
            </div><br><br>
            <select v-model="pickup" name="pickup">
                <option value="1">Leuven</option>
                <option value="2">Mechelen</option>
                <option value="3">Charleroi</option>
                <option value="4">Namur</option>
                <option value="5">Hasset</option>
            </select><br><br>
            <select v-if="pickup === '1'" v-model="pickuploc" name="pickuploc">
                <option value="1">Leuven 1</option>
                <option value="2">Leuven 2</option>
                <option value="3">Leuven 3</option>
                <option value="4">Leuven 4</option>
                <option value="5">Leuven 5</option>
            </select><br><br>
            <select v-if="pickup === '2'" v-model="pickuploc" name="pickuploc">
                <option value="1">Mechelen 1</option>
                <option value="2">Mechelen 2</option>
                <option value="3">Mechelen 3</option>
                <option value="4">Mechelen 4</option>
                <option value="5">Mechelen 5</option>
            </select><br><br>
            <select v-if="pickup === '3'" v-model="pickuploc" name="pickuploc">
                <option value="1">Charleroi 1</option>
                <option value="2">Charleroi 2</option>
                <option value="3">Charleroi 3</option>
                <option value="4">Charleroi 4</option>
                <option value="5">Charleroi 5</option>
            </select><br><br>
            <select v-if="pickup === '4'" v-model="pickuploc" name="pickuploc">
                <option value="1">Namur 1</option>
                <option value="2">Namur 2</option>
                <option value="3">Namur 3</option>
                <option value="4">Namur 4</option>
                <option value="5">Namur 5</option>
            </select><br><br>
            <select v-if="pickup === '5'" v-model="pickuploc" name="pickuploc">
                <option value="1">Hasset 1</option>
                <option value="2">Hasset 2</option>
                <option value="3">Hasset 3</option>
                <option value="4">Hasset 4</option>
                <option value="5">Hasset 5</option>
            </select><br><br>
            <input type="date" v-model="date"><br><br>
            <input type="time" v-model="time">
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
        max: Number
    },
    data() {
        return {
            count: 1,
            reRender: 0,
            pickup: '',
            pickuploc: '',
            date: '',
            time: ''
        }
    },
    methods: {
        increaseCount() {
            if (this.count < this.max) {
                this.count += 1
                this.reRender += 1
            }
        },
        decreaseCount() {
            if (this.count > 1) {
                this.count -= 1
                this.reRender += 1
            }
        },
        onSubmit(e) {
            e.preventDefault()
            if (!this.pickup) {
                alert('Please add a pickup')
                return
            }
            if (!this.date) {
                alert('Please add a date')
                return
            }
            if (!this.time) {
                alert('Please add a time')
                return
            }
            const newProduct = {
                type: "product",
                image: this.image,
                name: this.title,
                count: this.count,
                pickup: this.pickup,
                date: this.date,
                time: this.time,
                price: this.price * this.count
            }

            this.$emit('add-product', newProduct)
            this.count = 1
            this.date = ''
            this.time = ''
        }
    },
    components: {
        AddToCart,
    }
}
</script>

<style scoped>
.col-md-4 {
    height: 70vh;
    overflow: hidden;
}
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
    margin-left: 2vh;
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
.minus {
    margin-left: 5vh;
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
    position: relative;
    top: -14vh;
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
select[name=pickuploc] {
    position: absolute;
    top: 15vh;
    left: 12vh;
}
#button {
    position: relative;
    top: -5vh;
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