<template>
  <v-app id="inspire">
    <v-parallax class="img"
      src="@/assets/images/img15.png"
      height = "700"
      jumbotron
    ><v-row
        align="center"
        justify="end"
      >
       <!-- <v-col class="text-right" cols="4">
          <h1 class="display-1 font-weight-thin mb-4">DCA Consulting</h1>
          <h4 class="display-3">Une expertise mondiale inegalée au service de nos clients en France!</h4>
        </v-col>-->
      </v-row>
    </v-parallax>
    <v-parallax
      dark
      src="https://images.assetsdelivery.com/compings_v2/malija/malija1511/malija151100023.jpg"
    >
      <v-row
        align="center"
        justify="center"
      >
      <v-col class="text-left" cols="12">
        <h1 class="display-1 font-weight-thin mb-4">DCA Consulting</h1>
        <p class="subheading">Les missions que nous entreprenons ont vocation à servir les intérêts à long terme de nos clients. Nous nous employons à définir avec eux une vision intégrée du changement et à la mettre en œuvre à leurs côtés. A cette fin, nous mobilisons le fonds commun d’expérience, de connaissances, de méthodes et d’outils du réseau mondial de DCA consulting, tout en développant des solutions originales et créatives, adaptées à chaque situation particulière. Dans la majorité de nos interventions, nous constituons des équipes mixtes client-DCA, pour garantir le réalisme des recommandations, l’efficacité de leur mise en œuvre, et des transferts de compétence assurant des résultats pérennes.</p>
        <p class="subheading">La clef de voûte de l’accompagnement proposé par DCA consulting réside dans l’articulation entre compétences géographiques, sectorielles et fonctionnelles. Nous approfondissons et élargissons en permanence nos domaines d’expertise, aujourd’hui répartis dans 22 pôles de compétences sectoriels et 12 pôles de compétences fonctionnels. La pertinence de ces pôles est constamment renouvelée à travers le recrutement de profils pointus et le développement de nouveaux outils.</p>
      </v-col>
      </v-row>
    </v-parallax>
    <v-divider class="separator"></v-divider>
    <h1 class="text-center display-1 font-weight-thin mb-4">Nos domaines de compétences</h1>
    <v-divider class="separator"></v-divider>

    <v-layout row wrap class="pb-8">
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Développement Informatique</strong> </v-card-title>
              <v-card-text>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Programmation Web</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Programmation Mobile</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Programmation Logiciel</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Programmation Fonctionelle</p>
              </v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong> Cybersécurité</strong></v-card-title>
              <v-card-text>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Tests d'intrusions</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Gestion de crises</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Sensibilisation</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Analyses statiques</p>
              </v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Systèmes embarqués</strong>  </v-card-title>
                <v-card-text>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Conceptions de cartes électroniques</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Réseaux de neurones</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Robotique</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Aéronautique</p>
                </v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Blockchain</strong>  </v-card-title>
                <v-card-text>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Smart-contracts</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Développement de plateforme d'échanges</p>
                </v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Graphismes</strong>  </v-card-title>
              <v-card-text>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Réalité virtuelle</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Développement graphiques</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Infographie appliquée aux jeux-vidéos</p>
              </v-card-text>
             </v-card>
          </v-flex>
          <v-flex xs6 md4>
             <v-card outlined  width="600" height="250px">
              <v-card-title class="size blue--text text--darken-4"> <strong>Gestion de projet</strong>  </v-card-title>
              <v-card-text>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Agile</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Plannification</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>MicrosoftProject / Pert</p>
                <p text class="padding size2" color="blue darken-4"><v-icon>mdi-menu-right </v-icon>Analyse de risques</p>

              </v-card-text>
             </v-card>
          </v-flex>
        </v-layout>
        <AppFooter/>
    </v-app>
</template>

<script>
import AppFooter from './AppFooter'

export default {
  components: { AppFooter }
}
</script>

<style scoped>
.img {
  height: 100%
}
.separator {
  font: bold
}
</style>
