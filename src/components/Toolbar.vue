<template>
  <nav>
<!-- Toolbar (set up of the text)-->

    <v-app-bar app dark
    hide-on-scroll color="black"
    height="65"
      >
      <!-- <v-app-bar-nav-icon @click="drawer = !drawer"> </v-app-bar-nav-icon> -->
      <router-link to="/" class="d-flex align-center">
      <img
        src="@/assets/images/logo.png"
        alt="XShield Logo"
        class="logo"
      />
    </router-link>
      <v-toolbar-items >
        <v-btn text class="ml-12" to="/AppHome">Home</v-btn>
        <v-btn text to="/metier">Services</v-btn>
        <v-btn text to="/equipe" >Our Team</v-btn>
        <v-btn text to="/contact">Contact</v-btn>
      </v-toolbar-items>

      <template v-if="$vuetify.breakpoint.smAndUp">
        <v-spacer></v-spacer>
<!-- Menu (subscribe/ sign in)-->
    <v-menu open-on-hover bottom offset-y>
      <template v-slot:activator="{ on }">
        <v-btn icon v-on="on">
          <v-icon v-if="seen" light class="display-1 ">mdi-account</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item >
            <v-btn color="black" text to="/subscribe" >Subscribe</v-btn>
            <v-btn color="black" text to="/signin">Sign in</v-btn>
        </v-list-item>
      </v-list>
    </v-menu>
      </template>
    </v-app-bar>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      seen: true,
      LoginMenu: [
        { text: 'Subscribe' },
        { text: 'Sign in' }
      ]
    }
  }
}
</script>
<style scoped>
.logo {
  height: 50px; /* Adjust the height of the logo image */
  width: auto;  /* Maintain aspect ratio */
  max-height: 100%; /* Ensure it doesn't exceed the height of the app bar */
}

</style>
