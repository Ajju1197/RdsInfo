<template>
  <div class="contactus-section">
    <div class="container-fluid section-headings">
      <h3>Contact Us</h3>
    </div>
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-6 mb-5">
          <div class="contact-card">
            <div class="each-details">
              <h4>
                <fa
                  :icon="['fas', 'map-marker-alt']"
                  style="font-size: 25px"
                  :style="{ color: 'white' }"
                  class="map-icon"
                />Address
              </h4>
              <p>Manjeera Majestic Commercial,</p>
              <p>Opp To Jntuh,Hitech city road,</p>
              <p>Kukatpally, Hyderabad,</p>
              <p>Telangana 500072</p>
            </div>
            <div class="each-details">
              <h4>Lets Talk</h4>
              <span><a href="tel:+91 40-29563887">+91 40-29563887</a></span>
            </div>
            <div class="each-details">
              <h4>
                <fa
                  :icon="['fas', 'envelope']"
                  style="font-size: 25px"
                  :style="{ color: 'white' }"
                  class="map-icon"
                />General Support
              </h4>
              <span
                ><a href="mailto:info@rdsinfotech.com"
                  >info@rdsinfotech.com</a
                ></span
              >
              <span>
                <a href="mailto:hr@rdsinfotech.com">hr@rdsinfotech.com</a></span
              >
            </div>
          </div>
        </div>
        <div class="col-lg-6">
          <div class="contact-us-form"></div>
        </div>
      </div>
    </div>
    <div class="map-location">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d15221.3069936212!2d78.393705!3d17.491909!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x81590ec7359ee666!2sManjeera%20Majestic%20Commercial!5e0!3m2!1sen!2sin!4v1636124357681!5m2!1sen!2sin"
        width="100%"
        height="250"
        style="border: 0"
        allowfullscreen=""
        loading="lazy"
      ></iframe>
    </div>
    <Footer />
  </div>
</template>
<script>
import Footer from '../components/footer.vue'
export default {
  components: {
    Footer,
  },
}
</script>
<style>
.section-headings h3 {
  text-align: center;
  font-size: 50px;
  font-weight: 700;
  margin: 50px auto;
  color: rgb(43, 38, 38);
  font-family: 'Leckerli One', cursive;
}
.contact-card {
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url(https://cdn.pixabay.com/photo/2019/06/28/00/17/architecture-4303279_1280.jpg);
  background-size: cover;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  color: #fff;
  padding: 100px 0;
  row-gap: 3em;
}
.each-details {
  padding-left: 20%;
  font-size: 20px;
  text-shadow: 0px 0px 2px #000;
  margin-bottom: 2em;
}
.each-details h4 {
  font-size: 20px;
}
.each-details p,
span a {
  font-size: 16px;
  color: #9df2fd;
}
.map-icon {
  margin-right: 5px;
}
</style>
