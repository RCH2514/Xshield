<template>
  <v-container
    fill-height
    fluid
    grid-list-xl>
    <v-layout
      justify-center
      wrap
    >
      <v-flex
        xs12
        md8
      >
        <material-card
          color="green"
          title="Edit Profile"
          text="Complete your profile"
        >
          <v-form ref="form">
            <v-container py-0>
              <v-layout wrap>
                <v-flex
                  xs12
                  md4
                >
                  <v-text-field
                      v-model = "jobtitle"
                      required
                      v-bind:disabled=  "true"
                      label = "Job Title"
                      v-bind:outlined = true
                      v-bind:rounded= true
                      />
                </v-flex>
                <v-flex
                  xs12
                  md8
                >
                    <v-text-field
                      v-model = "username"
                      required
                      v-bind:disabled= true
                      label = "Mail"
                      v-bind:outlined = true
                      v-bind:rounded= true
                    ></v-text-field>
                </v-flex>
                <v-flex
                  xs12
                  md6
                >
                    <v-text-field
                      required
                      v-model = "Firstname"
                      v-bind:disabled=  true
                      label = "First Name"
                      v-bind:outlined = true
                      v-bind:rounded= true
                    ></v-text-field>
                </v-flex>
                <v-flex
                  xs12
                  md6
                >
                    <v-text-field
                      v-model = "Lastname"
                      required
                      v-bind:disabled= true
                      label = "Last Name"
                      v-bind:outlined = true
                      v-bind:rounded= true
                    ></v-text-field>
                </v-flex>
                <v-flex
                  xs12
                  md4>
                  <v-text-field
                    v-model = "country"
                      required
                      v-bind:disabled=  true
                      label = "Country"
                      v-bind:outlined = true
                      v-bind:rounded= true
                      />
                </v-flex>
                <v-flex
                  xs12
                  md4>
                  <v-text-field
                    v-model="city"
                    label="City"
                    class="purple-input"/>
                </v-flex>
                <v-flex
                  xs12
                  md4>
                  <v-text-field
                    v-model="postalCode"
                    class="purple-input"
                    label="Postal Code"
                    type="number"/>
                </v-flex>
                <v-flex xs12>
                  <v-textarea :key="componentKey"
                    v-model="projectText"
                    class="purple-input"
                    label="Soumettez-nous votre projet ici."
                    value="Soumettez-nous votre projet ici."
                  />
                </v-flex>
                <v-flex
                  xs12
                  text-xs-right
                >
                  <v-btn
                    class="mx-0 font-weight-light"
                    color="success"
                    @click="updateProfileInformations"
                  >
                    Update Profile
                  </v-btn>
                  <v-btn
                    class="ml-5 font-weight-light"
                    color="error"
                    @click="deleteProject"
                  >
                    Delete Project
                  </v-btn>
                  <div v-if="updateprofile" class="pt-5">
                    <v-row justify="space-around">
                      <h4 class="green--text">Thanks for updating your post ! </h4>
                    </v-row>
                  </div>
                  <div v-if="deleteprofile" class="pt-5" >
                    <v-row justify="space-around">
                      <h4 class="red--text">Your project is delete from our database !</h4>
                    </v-row>
                  </div>
                </v-flex>
              </v-layout>
            </v-container>
          </v-form>
        </material-card>
      </v-flex>
      <v-flex
        xs12
        md4
      >
        <material-card class="v-card-profile">
          <v-avatar
            slot="offset"
            class="mx-auto d-block"
            size="130"
          >
            <img
              src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSTBZMuk4s3xE4oXZNZ6TNCbFeEhQY4Xmh13j8FWN2eBzGM41yy&s"
            >
          </v-avatar>
          <v-card-text class="text-xs-center">
            <v-row justify="space-around" class="pt-5"><h1>WELCOME {{ Firstname }} ! </h1></v-row>
            <h4 class="category text-gray font-weight-thin mb-3 pt-3">{{ jobtitle}}</h4>
            <h2 class="card-title font-weight-light">{{ Firstname }}  {{ Lastname }} </h2>
            <v-btn
              class="ml-5 font-weight-light"
              color="error"
              @click="logout"
            >
              Logout
            </v-btn>
          </v-card-text>
        </material-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>

export default {
  data () {
    return {
      username: '',
      Firstname: '',
      Lastname: '',
      date: '',
      jobtitle: '',
      country: '',
      projectText: '',
      city: '',
      postalCode: '',
      updateprofile: false,
      deleteprofile: false,
      componentKey: 0,
      url: '' // 'http://localhost:3000'
    }
  },
  validate () {
    if (this.$refs.form.validate()) {
      this.snackbar = true
    }
  },
  reset () {
    this.$refs.form.reset()
  },
  created () {
    this.getProfileInformations()
  },
  methods: {
    // Login back end
    async getProfileInformations () {
      var emailStored = localStorage.getItem('email')
      var that = this
      // connecter l'utilisateur
      this.axios({
        method: 'post',
        url: this.url + '/api/profileInformations',
        data: {
          email: emailStored
        }
      })
        .then(function (response) {
        // On traite la suite une fois la réponse obtenue
          const status = JSON.parse(response.data.status)
          // redirect logic
          // eslint-disable-next-line eqeqeq
          if (status == '200') {
            that.Firstname = response.data.Firstname
            that.Lastname = response.data.Lastname
            that.username = response.data.username
            that.date = response.data.date
            that.jobtitle = response.data.jobtitle
            that.country = response.data.country
            that.projectText = response.data.projectText
            that.city = response.data.city
            that.postalCode = response.data.postalCode
          }
        })
        .catch(function (erreur) {
          // On traite ici les erreurs éventuellement survenues
        })
    },
    async updateProfileInformations () {
      // connecter l'utilisateur
      var that = this
      this.axios({
        method: 'post',
        url: this.url + '/api/updateprofile',
        data: {
          username: this.username,
          projectText: this.projectText,
          city: this.city,
          postalCode: this.postalCode
        }
      })
        .then(function (response) {
          that.updateprofile = true
        })
    },
    async deleteProject () {
      // connecter l'utilisateur
      var that = this
      this.axios({
        method: 'post',
        url: this.url + '/api/deleteProject',
        data: {
          username: this.username
        }
      })
        .then(function (response) {
          that.projectText = ''
          that.componentKey += 1
          that.updateprofile = false
        })
    },
    async logout () {
      localStorage.removeItem('email')
      this.$router.push('/')
    }
  },
  mounted () {
    if (sessionStorage.city) {
      this.city = sessionStorage.city
    }
    if (sessionStorage.postalCode) {
      this.postalCode = sessionStorage.postalCode
    }
    if (sessionStorage.projectText) {
      this.projectText = sessionStorage.projectText
    }
  },
  watch: {
    city (newCity) {
      sessionStorage.city = newCity
    },
    postalCode (newcode) {
      sessionStorage.postalCode = newcode
    },
    projectText (newProject) {
      sessionStorage.projectText = newProject
    }
  }
}
</script>

<style scoped>
</style>
