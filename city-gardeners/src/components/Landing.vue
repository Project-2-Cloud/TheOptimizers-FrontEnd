<template>
    <div class="wrapper">
        <div id="title" class="fluid-container">
            <div id="screen"></div>
            <img id="logo" src="logo.png" alt="logo">
            <h1>City Gardeneres</h1>
            <p>Fresh Vegetable plucked for you, from the garden in your city.</p>
        </div>
        <div id="about" class="fluid-container">
            <img class="bg" src="images/2.png" alt="">
            <div id="about-text" class="col-md-5 col-md-push-1 col-xs-8 col-xs-push-2">
                <h2>About our Initiative</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec iaculis enim. Maecenas eu augue pharetra, suscipit nisl nec, pellentesque velit. Morbi laoreet, nibh id lacinia condimentum, ex lectus iaculis dolor, a commodo tortor risus non nisi. Sed dictum molestie lorem, vel blandit lacus condimentum vel. Maecenas vitae porttitor diam, et elementum lectus.</p>
            </div>
            <img id="fruits" class="col-md-4 col-md-push-1 col-xs-8 col-xs-push-2" src="images/3.png" alt="fruits and veggies">
        </div>
        <div id="contact-points" class="container-fluid">
            <img class="bg" src="images/4.png" alt="">
            <div id="map-container" class="col-md-6 col-xs-12">
                <iframe id="map" title="map" src="https://www.google.com/maps/embed?pb=!1m16!1m12!1m3!1d23269.52492371014!2d4.690949079061041!3d50.87601079881467!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!2m1!1spost.nl%20contact%20points%20leuven!5e0!3m2!1sen!2sbe!4v1617101916839!5m2!1sen!2sbe"  width="400" height="300" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
            </div>
            <div id="contact-text" class="col-md-6 col-xs-12">
                <div class="text-center">
                    <h2>Our current contact points</h2>
                    <p>On this map you can see all of our current contact points! We plan to expand this, are there non yet near you? Feel free to let us know to excellerate the progress!</p>
                </div>
            </div>
        </div>
        <div id="signup" class="container-fluid">
            <img class="bg" src="images/5.png" alt="">
            <div class="row">
                <div class="col-md-6 col-xs-12">
                    <h2>For Customers</h2>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec iaculis enim.</p>
                    <Button text="Start Ordering" />
                </div>
                <div class="col-md-6 hidden-sm hidden-xs">
                    <img src="images/7.png" alt="">
                </div>
            </div>
            <div class="row">
                <div class="col-md-6 hidden-sm hidden-xs">
                    <img src="images/6.png" alt="">
                </div>
                <div class="col-md-6 col-xs-12">
                    <h2>For Sellers</h2>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec iaculis enim.</p>
                    <Button text="Start Selling" />
                </div>
            </div>
        </div>
        <div id="testimonials" class="fluid-container">
            <img class="bg" src="images/8.png" alt="">
            <h2>What our Customers Say</h2>
            <div class="row">
                <div class="col-md-4 col-xs-12">
                    <img class="testi-img" src="https://source.unsplash.com/200x200/?man" alt="">
                    <h4>Crystal Buckner</h4>
                    <p>Testimonials are short quotes from people who love your brand. It's a great way to convince customers to try your services.</p>
                </div>
                <div class="col-md-4 col-xs-12">
                    <img class="testi-img" src="https://source.unsplash.com/200x200/?women" alt="">
                    <h4>Crystal Buckner</h4>
                    <p>Testimonials are short quotes from people who love your brand. It's a great way to convince customers to try your services.</p>
                </div>
                <div class="col-md-4 col-xs-12">
                    <img class="testi-img" src="https://source.unsplash.com/201x201/?women" alt="">
                    <h4>Crystal Buckner</h4>
                    <p>Testimonials are short quotes from people who love your brand. It's a great way to convince customers to try your services.</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Button from './Button'

export default {
    name: 'Landing',
    components: {
        Button,
    }
}
</script>

<style scoped>
/* Title section */
#title {
    height: 100vh;
    padding: 20vh 15vw;
    text-align: center;
    background-size: cover;
}
#screen {
    position: absolute;
    height: 60vh;
    width: 70vw;
    background: white;
    opacity: 0.7;
    z-index: 0;
}
#title #logo {
    position: relative;
    height: 12vh;
    width: 12vh;
    margin: 7vh auto;
}
#title h1 {
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: green;
    font-size: 6vw;
    font-weight: 600;
}
#title p {
    position: relative;
    font-family: 'Lora', serif;
    color: green;
    font-size: 2.2vw;
}
@media only screen and (max-width: 1024px) {
    #title p  {
        margin-top: 6vh;
        font-size: 4vw;
    }
}

/* About section */
#about {
    height: 100vh;
    overflow: hidden;
    position: relative;
}
#about #fruits {
    position: relative;
    top: 50%;
    transform: translateY(-50%);
}
#about #about-text {
    top: 50%;
    transform: translateY(-50%);    
    text-align: center;
}
#about #about-text h2 {
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: green;
    font-size: 3vw;
    font-weight: 600;
}
#about #about-text p {
    position: relative;
    font-family: 'Lora', serif;
    color: green;
    font-size: 1.5vw;
}
@media only screen and (max-width: 991px) {
    #about #about-text  {
        top: 30%;
        font-size: 4vw;
    }
    #about #fruits {
        top:40%;
    }
    #about #about-text h2 {
        font-size: 5vw;
    }
    #about #about-text p {
        font-size: 2.1vw;
    }
}
@media only screen and (max-width: 575px) {
    #about #about-text p {
        font-size: 3vw;
    }
}

/* Contact Points Section */
#contact-points {
    height: 100vh;
    overflow: hidden;
    position: relative;
    background-color: darkgreen;
}
#contact-points #map-container {
    position: relative;
    top: 50%;
    transform: translateY(-50%);
    text-align: center;
    height: 40vw;
    opacity: 0.8;
}
#contact-points #map {
    height: 100%;
    width: 40vw;
}
#contact-points #contact-text {
    top: 50%;
    transform: translateY(-50%);    
    text-align: center;
}
#contact-points #contact-text h2 {
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: white;
    font-size: 3vw;
    font-weight: 600;
}
#contact-points #contact-text p {
    position: relative;
    font-family: 'Lora', serif;
    color: white;
    font-size: 1.5vw;
}

/* Signup Button Section */
#signup {
    padding: 5vh;
    height: 100vh;
    overflow: hidden;
    position: relative;
}
#signup .row {
    height: 47.5vh;
}
#signup .row img {
    height: 47.5vh;
}
#signup .row div {
    height: 47.5vh;
    text-align: center;
}
#signup .row h2 {
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: green;
    font-size: 3vw;
    font-weight: 600;
    margin: 5vh 0;
}
#signup .row p {
    position: relative;
    font-family: 'Lora', serif;
    color: green;
    font-size: 1.5vw;
    margin: 5vh 0;
}
#signup .row button {
    height: 10vh;
}
@media only screen and (max-width: 991px) {
    #signup .row h2 {
        font-size: 5vw;
    }
    #signup .row p {
        font-size: 2vh;
    }
}


/* Testimonial Section */
#testimonials {
    padding: 2vw;
    height: 100vh;
    overflow: hidden;
    position: relative;
    background-color: darkgreen;
}
#testimonials div {
    text-align: center;
}
#testimonials h2 {
    text-align: center;
    position: relative;
    font-family: 'Montserrat', sans-serif;
    text-transform: uppercase;
    color: white;
    font-size: 3vw;
    font-weight: 600;
    top: 5vh;
}
#testimonials .testi-img {
    height: 15vh;
    border-radius: 50%;
}
#testimonials h4 {
    position: relative;
    font-family: 'Lora', serif;
    color: white;
    font-size: 2vw;
    font-weight: 700;
}
#testimonials p {
    position: relative;
    font-family: 'Lora', serif;
    color: white;
    font-size: 1.5vw;
}
#testimonials .row {
    position: relative;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
#testimonials .row div {
    margin: 2vh 0;
}
@media only screen and (max-width: 991px) {
    #testimonials h2 {
        font-size: 5vw;
    }
    #testimonials h4 {
        font-size: 3vh;
    }
    #testimonials p {
        font-size: 2vh;
    }
    #testimonials .testi-img {
        height: 10vh;
    }
}
</style>