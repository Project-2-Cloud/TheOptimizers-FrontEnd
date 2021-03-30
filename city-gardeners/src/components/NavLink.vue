<template>
    <div id="link">
        <p>{{ minor }}</p>
        <h5>{{ text }}</h5>
    </div>
</template>

<script>
export default {
    name: 'NavLink',
    props: {
        text: String,
        minor: String,
    }
}
</script>

<style scoped>
#link {
    float: right;
    color: green;
    text-decoration: none;
    margin-right: 2.5vw;
    margin-top: 3vh;
    cursor: pointer;
}
#link h5 {
    font-size: 2vh;
    margin: 0;
}
#link p {
    font-size: 1.5vh;
    margin: 0;
}
</style>