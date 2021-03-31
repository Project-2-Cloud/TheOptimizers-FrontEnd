<template>
    <div id="workshop" class="container-fluid">
        <h2 id="workshop-title">Gardening Workshops</h2>
        <div id="screen" @click="deselect()" class="container-fluid"></div>
        <div class="row">
            <Workshop :id="'workshop' + workshop.id" :key="workshop.id" v-for="workshop in workshops" @workshop-select="selectWorkshop(workshop.id)" :title="workshop.title" :price="workshop.price" :image="workshop.image" />
        </div>
    </div>
</template>

<script>
import Workshop from "./Workshop"

export default {
    name: 'WorkShops',
    components: {
        Workshop
    },
    methods: {
        selectWorkshop(id) {
            var element = "workshop"+id
            document.getElementById("screen").style.visibility = "visible"
            document.getElementById(element).setAttribute('id', 'selected')
            this.lastSelected = id;
        },
        deselect() {
            document.getElementById("screen").style.visibility = "hidden"
            document.getElementById("selected").setAttribute('id', "workshop"+this.lastSelected)
        }
    },
    data() {
        return {
            workshops: [],
            lastSelected: null,
        }
    },
    created() {
        this.workshops = [
                {
                    id: 0,
                    title: "Fencing",
                    price: 50.00,
                    image: "images/Workshops/1.png"
                },
                {
                    id: 1,
                    title: "Beautify",
                    price: 49.00,
                    image: "images/Workshops/2.png"
                },
                {
                    id: 2,
                    title: "Manure",
                    price: 20.00,
                    image: "images/Workshops/3.png",
                },
                {
                    id: 3,
                    title: "Plants",
                    price: 39.00,
                    image: "images/Workshops/4.png",
                },
                {
                    id: 4,
                    title: "Fertilizers",
                    price: 99.00,
                    image: "images/Workshops/5.png",
                },
                {
                    id: 5,
                    title: "Planting",
                    price: 40.00,
                    image: "images/Workshops/6.png",
                },
            ]
    }
}
</script>

<style scoped>
#workshop {
    background-color: #FFE;
}
#workshop-title {
    text-align: center;
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: green;
    font-size: 6vh;
    font-weight: 600;
    margin-top: 15vh;
}
.row {
    margin: 10vh 10vw;
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