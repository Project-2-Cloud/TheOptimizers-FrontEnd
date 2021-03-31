<template>
    <div id="workshop" class="container-fluid">
        <h2 id="workshop-title">Gardening Workshops</h2>
        <div class="row">
            <Workshop title="Fencing" price="50.00" image="images/Workshops/1.png" />
            <Workshop title="Beautify" price="49.00" image="images/Workshops/2.png" />
            <Workshop title="Manure" price="20.00" image="images/Workshops/3.png" />
            <Workshop title="Plants" price="39.00" image="images/Workshops/4.png" />
            <Workshop title="Fertilizers" price="99.00" image="images/Workshops/5.png" />
            <Workshop title="Planting" price="40.00" image="images/Workshops/6.png" />
        </div>
    </div>
</template>

<script>
import Workshop from "./Workshop"

export default {
    name: 'WorkShops',
    components: {
        Workshop
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
</style>