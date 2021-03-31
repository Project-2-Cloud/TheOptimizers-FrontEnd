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
    color: green;
    text-decoration: none;
    margin: 3vh 0 0 2.5vw;
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