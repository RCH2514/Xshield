<template>
  <v-container >
    <h1 class="pt-5 ContactTitle">Subscribe to DCA Consulting Corporation</h1>
    <p class="grey--text">Enter your name and email address, personal information and click “Subscribe”.</p>
   <v-card  class="mt-8 pb-12 mx-auto " width="1100" height="1150px" >
      <v-img
        class="white--text"
        height="200px"
        src="https://www.docusign.fr/blog/wp-content/uploads/sites/14/2015/10/shutterstock_182769413-Converted-720x542.png"
      >
      <!-- <strong><v-card-title class="align-end black--text justify-center">SUBSCRIBE</v-card-title></strong> -->
      </v-img>
        <v-form class="px-3" ref="form" v-model="valid" lazy-validation>

      <v-text-field
        class="black--text"
        prepend-icon="mdi-account"
        v-model="Firstname"
        :counter="20"
        :rules="FirstnameRules"
        label="Firstname"
        required>
      </v-text-field>

      <v-text-field
        class="black--text"
        prepend-icon="mdi-account"
        v-model="Lastname"
        :counter="20"
        :rules="LastnameRules"
        label="Last Name"
        required>
      </v-text-field>

      <v-text-field
        prepend-icon="mdi-email"
        v-model="email"
        :rules="emailRules"
        label="E-mail"
        required>
      </v-text-field>

      <v-menu
      ref="menu"
      v-model="menu"
      :close-on-content-click="false"
      transition="scale-transition"
      >
        <template  v-slot:activator="{ on }">
          <v-text-field
          v-model="date"
          label="Birth date"
          prepend-icon="mdi-calendar"
          readonly
          v-on="on">
          </v-text-field>
        </template>
        <v-date-picker
        ref="picker"
        v-model="date"
        :max="new Date().toISOString().substr(0, 10)"
        min="1950-01-01"
        @change="save">
        <v-btn text color="primary" @click="menu = false">Cancel</v-btn>
          <v-btn text color="primary" @click="$refs.menu.save(date)">OK</v-btn>
        </v-date-picker>
      </v-menu>

       <v-text-field
        class="black--text"
        prepend-icon="mdi-account-card-details"
        v-model="jobtitle"
        :rules="JobTitleeRules"
        label="Job title"
        required>
      </v-text-field>

      <v-row align="center">
        <v-col cols="6">
          <v-subheader>Select Country</v-subheader>
        </v-col>
        <v-col cols="6">
          <v-select
            v-model="e1"
            :items="states"
            :rules="CountryRules"
            menu-props="auto"
            label="Select"
            hide-details
            prepend-icon="mdi-map"
            single-line
          ></v-select>
        </v-col>
      </v-row>

      <v-card-text class=" pt-10 text-left" > Vous êtes :</v-card-text>

      <v-radio-group column class="pl-12">
        <v-radio label="Une femme"></v-radio>
        <v-radio label="Un homme"></v-radio>
      </v-radio-group>

      <v-text-field
        prepend-icon="mdi-lock-question"
        v-model="password"
        type="password"
        :rules="passwordRules"
        label="Password"
        required>
      </v-text-field>

      <v-text-field
        prepend-icon="mdi-lock-question"
        v-model="Confirmpassword"
        type="password"
        :rules="ConfirmpasswordRules"
        label="Confirm Password"
        required>
      </v-text-field>

    <!-- popup privacy policy -->
<v-dialog v-model="popup" width="600px">
  <template v-slot:activator="{ on }">
    <v-btn small depressed color="primary" dark v-on="on">Privacy policy</v-btn>
  </template>
    <v-card>
      <v-card-title>
        <span class="headline">Society privacy policy</span>
      </v-card-title>
        <v-card-text>This Privacy Policy applies to the website(s) and mobile applications (together, the "Sites") provided by DCA Consulting Corporation, a company headquartered in Boston, Massachusetts, USA, and/or the other companies of the DCA group ("DCA", “we”, “us”) who act as data controllers[1] with respect to the personal data you share with DCA under this Policy.
The Sites include www.DCA.com and additional websites or mobile applications produced and managed by DCA. Please note that this Privacy Policy does not apply to the following websites:
    the DCA Extranet (bcp.DCA.com), which is accessible from the www.DCA.com site but is governed by a separate policy contained in our agreements with Bain clients that are provided access to the Extranet; or
    the DCA Alumni Job Board (careercenter.DCA.com), which is provided and managed by a third party and is governed by a separate privacy policy.
DCA knows that your privacy is important to you and takes user privacy very seriously. We are committed to protecting your personal data[2] (i.e. any information you provide to us from which you can be identified) in accordance with this Privacy Policy.
DCA reserves the right, at its sole discretion, to alter and update this Privacy Policy from time to time. We therefore invite you to review the current version of the Privacy Policy each time you return to our Sites.
Some terms are defined throughout this Policy. Simply hover over the terms in bold to obtain their definition.
          +</v-card-text>
      </v-card>
</v-dialog>

      <v-checkbox
      v-model="checkbox"
      :rules="[v => !!v || 'You must agree to continue']"
      label="By signing up I agree to the Society terms & conditions and privacy policy."
      required
    ></v-checkbox>

       <v-btn large :disabled="!valid" color="success" class="mr-4" @click="Submit"> Submit </v-btn>
      <v-btn large color="error" class="mr-4" @click="reset"> Clear</v-btn>
      <router-link to="/signin">
        <v-card-text class="black--text ">Already menbers? Log In</v-card-text>
      </router-link>
      </v-form>
    </v-card>
    <AppFooter class="footerSpace"/>
  </v-container>
</template>

<script>
import AppFooter from './AppFooter'

export default {
  components: { AppFooter },
  data () {
    return {
      // date
      url: '', // 'http://localhost:3000',
      subscribe: false,
      e1: 'France',
      date: null,
      menu: false,
      popup: false,
      watch: {
        menu (val) {
          val && setTimeout(() => (this.$refs.picker.activePicker = 'YEAR'))
        }
      },
      // country
      states: [
        'France', 'Belgium', 'American Samoa', 'Arizona',
        'Arkansas', 'California', 'Colorado', 'Connecticut',
        'Delaware', 'District of Columbia', 'Federated States of Micronesia',
        'Florida', 'Georgia', 'Guam', 'Hawaii', 'Idaho',
        'Illinois', 'Indiana', 'Iowa', 'Kansas', 'Kentucky',
        'Louisiana', 'Maine', 'Marshall Islands', 'Maryland',
        'Massachusetts', 'Michigan', 'Minnesota', 'Mississippi',
        'Missouri', 'Montana', 'Nebraska', 'Nevada',
        'New Hampshire', 'New Jersey', 'New Mexico', 'New York',
        'North Carolina', 'North Dakota', 'Northern Mariana Islands', 'Ohio',
        'Oklahoma', 'Oregon', 'Palau', 'Pennsylvania', 'Puerto Rico',
        'Rhode Island', 'South Carolina', 'South Dakota', 'Tennessee',
        'Texas', 'Utah', 'Vermont', 'Virgin Island', 'Virginia',
        'Washington', 'West Virginia', 'Wisconsin', 'Wyoming'
      ],
      CountryRules: [ v => !!v || 'Country is required' ],
      // firstname
      valid: true,
      Firstname: '',
      FirstnameRules: [
        v => !!v || 'FirstName is required',
        v => (v && v.length <= 20) || 'Name must be less than 10 characters'
      ],
      // lastname
      Lastname: '',
      LastnameRules: [
        v => !!v || 'LastName is required',
        v => (v && v.length <= 20) || 'Name must be less than 10 characters'
      ],
      // Job title
      jobtitle: '',
      JobTitleeRules: [
        v => !!v || 'Job Title is required'
      ],
      //  email
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid'
      ],
      //  password
      password: '',
      Confirmpassword: '',
      passwordRules: [
        v => !!v || 'password is required'
      ],
      //  Confirmpassword
      ConfirmpasswordRules: [
        v => !!v || 'Confirmpassword is required'
      ],
      //  checkbox
      checkbox: false
    }
  },
  methods: {
    // Subscribe Back End
    async Submit () {
      this.validate()
      if (this.snackbar !== true) {
        return
      }

      this.axios({
        method: 'post',
        url: this.url + '/api/subscribe',
        data: {
          email: this.email,
          password: this.password,
          Firstname: this.Firstname,
          Lastname: this.Lastname,
          date: this.date,
          jobtitle: this.jobtitle,
          country: 'France'
        }
      })
        .then((response) => {
          alert('Thank you for suscribing on DCA Consulting Company!')
          this.$router.push('signin')
        }, (error) => {
          console.log(error)
        })
    },
    reset () {
      this.$refs.form.reset()
    },
    rememberMe () {
    },
    save (date) {
      this.$refs.menu.save(date)
    },
    validate () {
      if (this.$refs.form.validate()) {
        this.snackbar = true
      }
    }
  }
}
</script>

<style  scoped>
.footerSpace{
  margin-top: 1cm;
  background: inherit
}
</style>
