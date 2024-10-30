<template>
<v-app>
  <v-container >
      <h3 class="pt-5 blue--text text--darken-4">A propos de DCA Consulting corporation</h3>
      <h1 class="pt-5 ContactTitle">Contactez-Nous</h1>
      <p class="pt-3 pb-10 TextContact">
        Nous vous remercions de l’intérêt que vous portez à <strong class="blue--text text--darken-4">DCA Consulting corporation</strong>.<br>
        Vous pouvez nous contacter à l’aide des coordonnées indiquées ci-dessous.
      </p >

        <v-layout row wrap class="pb-8">
           <v-flex xs6 md4 v-for="information in contact" :key="information.id">
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong> Bureau de Paris</strong></v-card-title>
              <div class="ml-3 pt-3">{{information.name}}</div>
              <div class="ml-3">{{information.adresse}}</div>
              <div class="ml-3">{{information.codePostal}}</div>
              <div class="ml-3">{{information.pays}}</div><br>
              <div class="ml-3">{{information.Telephone}}</div>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Demande de mission de conseil</strong> </v-card-title>
              <v-card-text>
                <v-btn text class="padding size2" color="blue darken-4" to="/signin"><v-icon>mdi-menu-right </v-icon>Soumettre votre requête</v-btn>
              </v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong> Réseaux sociaux</strong></v-card-title>
              <v-card-text>
                <v-btn text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Suivez-nous sur Facebook, Twitter et Instagram</v-btn>
              </v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Relations Presse</strong>  </v-card-title>
              <v-card-text class="mt-5 "><a href="mailto:conteh@et.esiea.fr">conteh@et.esiea.fr</a></v-card-text>
              <v-card-text class="mt-n10"><a href="mailto:soumaila@et.esiea.fr">soumaila@et.esiea.fr</a></v-card-text>
              <v-card-text class="mt-n10"><a href="mailto:azakkour@et.esiea.fr">azakkour@et.esiea.fr</a></v-card-text>
              <v-card-text class="mt-n5"><a href="mailto:azakkour@et.esiea.fr">Paris.Marketing@DCACorporation.fr</a></v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Recrutement</strong> </v-card-title>
              <v-card-text class="mt-5 "><a href="mailto:soumaila@et.esiea.fr">soumaila@et.esiea.fr</a></v-card-text>
              <v-card-text class="mt-n10"><a href="mailto:azakkour@et.esiea.fr">azakkour@et.esiea.fr</a></v-card-text>
              <v-card-text class="mt-n5"><a href="mailto:azakkour@et.esiea.fr">Paris.Recruiting@DCACorporation.fr</a></v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Question ou commentaires</strong>  </v-card-title>
              <v-card-text>
                <v-btn text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon><a href="mailto:Paris.Recruiting@DCACorporation.fr">Contacter-Nous</a></v-btn>
              </v-card-text>
             </v-card>
          </v-flex>
        </v-layout>

      <p class="pt-3 pb-10 TextContact">
        "Les meilleures choses qui arrivent dans le monde de l’entreprise ne sont pas le résultat du travail d’un seul homme. C’est le travail de toute une équipe." <br><br><strong>Steve JOBS</strong>
      </p >

         <v-row>
      <v-col cols="6" sm="4">
        <v-img
          src="https://cdn.pixabay.com/photo/2017/04/03/17/24/teamwork-2198961_1280.png"
        ></v-img>
      </v-col>

      <v-col cols="6" sm="4">
        <v-img src="https://cdn.pixabay.com/photo/2018/03/28/09/44/document-3268750_1280.jpg">
          <div class="fill-height bottom-gradient"></div>
        </v-img>
      </v-col>

      <v-col cols="6" sm="4">
        <v-img src="https://cdn.pixabay.com/photo/2016/12/19/10/16/hand-1917895_1280.png">
          <div class="fill-height repeating-gradient"></div>
        </v-img>
      </v-col>
    </v-row>
    </v-container>
    <AppFooter class="pa-0"/>
</v-app>
</template>

<script>
import AppFooter from './AppFooter'

export default {
  components: { AppFooter },
  data () {
    return {
      contact: [
        { name: 'DCA consulting Corporation', adresse: '1 Infinite Loop', codePostal: 'CA 95014', pays: 'Etats-Unis', Telephone: 'Téléphone : +33 1 44 55 75 75' }
      ]
    }
  }
}
</script>

<style scoped>
.ContactTitle {
  font-size: 40px
}
.TextContact{
  font-size: 30px
}
.padding {
  bottom: -100px;
}
.size {
   font-size: 25px
}
.size2 {
   font-size: 12px
}
</style>
