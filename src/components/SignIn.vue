<template>
  <v-container>
    <h1 class="pt-5 ContactTitle">Sign In to DCA Consulting Corporation</h1>
    <p class="grey--text">Sign in to access to your profile.</p>
   <v-card  class="mt-8 mx-auto " max-width="1000" height="520px" >
       <v-img
        class="white--text"
        height="200px"
        src="http://2op.com.br/blog/wp-content/uploads/2015/12/redacao-on-principais-caracteristicas-da-producao-de-conteudo-1000x563.jpg"
      >
      <!-- <strong><v-card-title class="align-end black--text justify-center ">SIGN IN</v-card-title></strong> -->
      </v-img>
        <v-form class="px-3" ref="form" v-model="valid" lazy-validation>

      <v-text-field
        prepend-icon="mdi-email"
        v-model="email"
        :rules="emailRules"
        label="E-mail"
        required>
      </v-text-field>

      <v-text-field
        prepend-icon="mdi-lock-question"
        v-model="password"
        type="password"
        :rules="passwordRules"
        label="Password"
        required>
      </v-text-field>

      <v-checkbox
        v-model="checkbox"
        :rules="checkboxRules"
        label="Remember Me"
        required>
      </v-checkbox>

      <v-btn small  :disabled="!valid" color="success" class="mr-4" @click="login"> LOGIN </v-btn>
      <v-btn small color="error" class="mr-4" @click="reset"> Clear</v-btn>
      <br><br>

      <v-btn small to="/subscribe">Subscribe</v-btn>
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
      url: '', // 'http://localhost:3000',
      valid: true,
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid'
      ],
      password: '',
      passwordRules: [ ],
      checkbox: false,
      checkboxRules: [ ]
    }
  },
  methods: {
    validate () {
      if (this.$refs.form.validate()) {
        this.snackbar = true
      }
    },
    reset () {
      this.$refs.form.reset()
    },
    rememberMe () {
    },
    // Login back end
    async login () {
      var that = this
      // connecter l'utilisateur
      this.axios({
        method: 'post',
        url: this.url + '/api/login',
        data: {
          email: this.email,
          password: this.password
        }
      })
        .then(function (response) {
        // On traite la suite une fois la réponse obtenue
          const status = JSON.parse(response.data.status)
          // redirect logic
          // eslint-disable-next-line eqeqeq
          if (status == '200') {
            localStorage.setItem('email', that.email)
            sessionStorage.clear()
            that.$router.push('profil')
          }
        })
        .catch(function (erreur) {
          // On traite ici les erreurs éventuellement survenues
          console.log(erreur)
        })
    }
  }
}
</script>

<style scoped>
.pt-10{
    margin: -10px 0 0 0;
    padding: 100px;
    position:absolute;
    left: 0;
    right: 0;
}
.footerSpace{
  margin-top: 1cm;
  background: inherit
}
</style>
