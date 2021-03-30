<template>
    <h2 id="workshop-title">Gardening Workshop</h2>
    <div class="row">
        <Workshop title="Workshop" image="images/9.png" />
        <Workshop title="Workshop" image="images/10.png" />
        <Workshop title="Workshop" image="images/11.png" />
        <Workshop title="Workshop" image="images/12.png" />
        <Workshop title="Workshop" image="images/13.png" />
        <Workshop title="Workshop" image="images/14.png" />
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
#workshop-title {
    text-align: center;
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: green;
    font-size: 3vw;
    font-weight: 600;
    margin-top: 15vh;
}
.row {
    margin: 10vh 10vw;
    text-align: center;
}
</style>