<template>
  <v-container>
    <v-layout row wrap class="image">
      <v-flex xs12 >
        <v-carousel cycle align="center" justify="end" height = "600" jumbotron>
          <v-carousel-item
            v-for="meetup in meetups"
            :src="meetup.imageUrl"
            :key="meetup.id"
            ;>
            <v-parallax class="img"
            src= meetup.imageUrl
            height = "600"
            jumbotron
          ><v-row
              align="end"
              justify="center"
              class="carousel-content"
            >
              <v-col class="text-center" cols="13">
                <h1 class="titr"> {{meetup.title}} </h1>
                <p class="subtext"> {{ meetup.subtext }} </p>
              </v-col>
            </v-row>
          </v-parallax>
          </v-carousel-item>
        </v-carousel>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      meetups: [
        { imageUrl: require('@/assets/images/img1.png'), subtext: 'Trusted by businesses to safeguard their digital assets with state-of-the-art protection.', id: 'image1', title: 'XShield: Your First Line of Defense Against Cyber Threats.', width: screen.width },
        { imageUrl: require('@/assets/images/img2.jpg'), id: 'image2', title: 'Expert Cybersecurity Solutions Tailored to Your Needs.', subtext: 'XShield adapts to the changing threat landscape to ensure your ongoing peace of mind.', width: screen.width },
        { imageUrl: require('@/assets/images/img3.jpg'), id: 'image3', title: 'Comprehensive Security That Evolves with Your Business. ', subtext: 'We keep our customers ahead of the changing cyber threat landscape everyday.', width: screen.width }
      ]
    }
  }
}
</script>

<style scoped>
  .text-center {
    position:inherit;
    background-color: rgba(0,0,0,0.2);
    color: white;
    padding-bottom: 80px;

  }
  .subtext {
    font-size: 20px;
    font-weight: 300;
    margin-top: 10px;
    line-height: 1.5;
    padding-left: 0;
    padding-left: 700px;
  }
  .titr {

    font-size:30px;
    font-family: Fkgrotesk, sans-serif;
    letter-spacing: 1px;
    font:bold;
    padding-left: 800px;
    padding-top: 0;
  }
</style>

<style scoped>
.image{
    position:absolute;
    left: 0;
    right: 0;
    top: 0;
}
</style>
