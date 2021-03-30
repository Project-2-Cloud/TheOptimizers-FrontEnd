<template>
    <div id="workshop" class="col-md-4 col-sm-6 col-xs-12">
        <h4>{{ title }}</h4>
        <img :src=image alt="">
    </div>    
</template>

<script>
export default {
    name: 'Workshop',
    props: {
        title: String,
        image: String,
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
}
#workshop img {
    height: 20vw;
    width: 20vw;
    margin-bottom: 5vh;
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