<template>
    <a>
        <p>{{ minor }}</p>
        <h5>{{ text }}</h5>
    </a>
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
a {
    float: right;
    color: green;
    text-decoration: none;
    margin-right: 2.5vw;
    margin-top: 3vh;
}
h5 {
    font-size: 2vh;
    margin: 0;
}
p {
    font-size: 1.5vh;
    margin: 0;
}
</style>