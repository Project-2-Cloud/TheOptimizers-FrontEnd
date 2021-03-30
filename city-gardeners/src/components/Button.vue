<template>
    <button @click="onClick">{{ text }}</button>
</template>

<script>

export default ({
    name: 'Button',
    props: {
        text: String
    },
    methods: {
        onClick() {
            console.log('Clicked')
        }
    }
})
</script>

<style scoped>
button {
    height: 10vh;
    width: 30vh;
    color: white;
    font-size: 3vh;
    font-weight: 700;
    background-color: darkgreen;
    border-radius: 2vh;
}
</style>