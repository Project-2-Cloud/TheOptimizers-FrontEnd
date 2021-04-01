<template>
    <div id="customer" class="container-fluid">
        <h2 id="customer-title">Customer Service</h2>
        <form @submit="onSubmit" class="col-lg-6 col-lg-push-3 col-md-8 col-md-push-2 col-xs-12">
            <section>
            <input type="text" placeholder="FirstName" v-model="firstName">
            <input type="text" placeholder="LastName" v-model="lastName">
            </section><br>
            <input type="email" placeholder="Email" v-model="email"><br>
            <div>
                <label for="Message">Message</label><br>
                <textarea name="message" id="" cols="30" rows="10" v-model="message"></textarea>
            </div>
            <Button id="submit" text="Send" type="submit" />
        </form>
    </div>
</template>

<script>
import Button from "./Button"

export default {
    name: 'Customer',
    components: {
        Button,
    },
    data() {
        return {
            firstName: '',
            lastName: '',
            email: '',
            message: ''
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()
            if(!this.firstName) {
                alert('Enter your First Name')
                return
            }
            if(!this.email) {
                alert('Enter a valid email')
                return
            }
            if(!this.message) {
                alert('Write a Message')
                return
            }
            alert('Message Sent! We will email you soon.')
            this.message = ''
        }
    }
}
</script>

<style scoped>
#customer {
    background-color: #16421D;
}
h2 {
    text-align: center;
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: lightgreen;
    font-size: 6vh;
    font-weight: 600;
    margin: 15vh 0 5vh 0;
}
form {
    text-align: center;
}
section {
    white-space: nowrap;
}
input {
    margin: 1vh 2vw;
    height: 5vh;
    width: 20vw;
    font-family: 'Montserrat', sans-serif;
    font-size: 3vh;
}
input[type=email] {
    width: 44vw;
    margin-bottom: 5vh;
}
label {
    font-family: 'Montserrat', sans-serif;
    color: lightgreen;
    font-size: 3vh;
}
textarea {
    align-items: center;
    width: 44vw;
    font-family: 'Montserrat', sans-serif;
    font-size: 3vh;
    margin-bottom: 10vh;
    border-radius: 10px;
    resize: none;
}
#submit {
    margin-bottom: 5vh;
}
</style>