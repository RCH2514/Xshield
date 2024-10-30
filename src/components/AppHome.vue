<template>
  <v-app id="inspire">
        <Carousel/>
        <div class="content-container">
      <!-- Image element -->
      <img src="@/assets/images/img4.jpg" alt="Descriptive Image Text" class="content-image"/>

      <!-- Text content -->
      <div class="text-content">
        <h3 style="color:#08BAEC; text-align: center;letter-spacing: 1px;font-weight: bold;font-family: Fkgrotesk, sans-serif;">XShield : L'Art de Sécuriser Votre Avenir Numérique</h3><br>
        At XShield, our startup is proudly rooted in Tunisia, where we bring together a team of dedicated cybersecurity students from Sup'Com. Our mission is to provide cutting-edge cybersecurity solutions and services tailored to meet the diverse needs of our clients. Leveraging our academic expertise and hands-on experience, we offer a comprehensive range of services including incident response, technical assurance, on-demand expertise, and cybersecurity transformation. Our team is committed to staying ahead of the curve in the rapidly evolving cybersecurity landscape, ensuring that our clients receive the highest level of protection and support. At XShield, we are passionate about securing your digital assets with precision and excellence.
      </div>
    </div>

        <h2 > Our latest projects</h2>
        <VerticalSeparator align="center" justify="center" style="padding-top:5px;"/>
      <carousel-3d  style="height: 650px;padding-top: 60px;">
            <slide :index="0" style="width: 500px;height: 450px;">
              <div class="card">
            <img src="@/assets/images/img5.png" alt="Slide Image" />
            <div class="card-bar">
              <h3>Automated Vulnerability Assessment and Management.</h3>
              <p>Our Automated Vulnerability Assessment and Management tool simplifies and streamlines the process of identifying and addressing security vulnerabilities across your IT infrastructure. This solution provides real-time scanning, automated vulnerability prioritization, and actionable remediation recommendations.</p>
            </div>
          </div>
            </slide>
            <slide :index="1"  style="width: 500px;height: 450px;">
             <div class="card">
            <img src="@/assets/images/img6.jpg" alt="Slide Image" />
            <div class="card-bar">
              <h3>Advanced Threat Detection System</h3>
              <p>Our Advanced Threat Detection System leverages cutting-edge machine learning algorithms to identify and neutralize sophisticated cyber threats in real-time. By analyzing network traffic patterns and user behavior, this system provides unparalleled accuracy in detecting anomalies and potential breaches </p>
            </div>
             </div>

           </slide>
           <slide :index="2" style="width: 500px;height: 450px;">
            <div class="card">
            <img src="@/assets/images/img7.jpg" alt="Slide Image" />
            <div class="card-bar">
              <h3>Zero Trust Security Framework Implementation </h3>
              <p>The Zero Trust Security Framework is a revolutionary approach to cybersecurity that assumes no implicit trust, regardless of whether users are inside or outside the network. Our implementation services include comprehensive assessments, tailored architecture designs, and seamless integration with existing systems. This project focuses on enforcing strict access controls, continuous verification of user identities, and micro-segmentation to protect your critical assets.</p>
            </div>
            </div>
           </slide>

</carousel-3d>
        <AppFooter class="footer"/>
   </v-app>
</template>

<script>
import Vue from 'vue'
import Carousel3d from 'vue-carousel-3d'
import VerticalSeparator from './VerticalSeparator'
import Carousel from './Carousel'
import AppFooter from './AppFooter'

Vue.use(Carousel3d)
export default {
  components: { Carousel, VerticalSeparator, AppFooter }
}
</script>

<style scoped>
  .text-center {
    position: relative;
    color: black;
    max-width: 1000px;
    top: 640px;
    font-size: 24px;
    margin-left: auto;
    margin-right: auto;
  }
  .team{
    position: relative;
    color: black;
    top: 640px;
    font-size: 20px;
    margin-left: auto;
    margin-right: auto;
  }
  .footer{
    top: 640px !important;
  }
  .content-container {
  display:flex;
  align-items: center;
  justify-content: center;
  gap: 12px; /* Adjust as needed for spacing */
  margin: 7px; /* Adjust as needed for margin */
  padding-top: 700px;
  padding-bottom: 0;
}

.content-image {
  max-width: 40%; /* Adjust as needed */
  height: auto;
  border-radius: 8px; /* Optional: for rounded corners */
}

.text-content {
  max-width: 60%; /* Adjust as needed */
  text-align: left; /* Ensure text is aligned left within the paragraph */
  padding-left: 5px;
}
.card {
  width: 100%;
  height: 100%;
  background-color: #fff;
  border-radius: 4px;
  box-shadow: 0 4px 15px 0 rgba(40,44,53,.06), 0 2px 2px 0 rgba(40,44,53,.08);
  position:absolute;
  cursor: pointer;
}

.card img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  transition: opacity 150ms linear;
      user-select: none;

      &:hover {
        opacity: 0.7;
      }
}

.card-bar {
  width: 100%;
  height: 100px;
}

.card-bar h3 {
  font-size: 20px;
  font-weight: bold;
}

.card-bar p {
  font-size: 12px;
  color: #666;
}
h2{
 font-family: StyreneA, sans-serif;font-weight: 700;font-size: calc(calc((100vw - 428px) / 1012* 12) + 36px);line-height: calc(calc((100vw - 428px) / 1012* 11) + 39px);letter-spacing: calc(calc((100vw - 428px) / 1012* .5) + -1.5px);
 padding-top: 80px;
 padding-left: 37%;
 color:#08BAEC;
}

</style>
