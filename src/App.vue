<template>
  <v-app app class ="app" min-height= "0" wrap>
    <v-content min-height= "0">
      <Toolbar/>
      <router-view></router-view>
    </v-content>
      <!-- <AppFooter/> -->

  </v-app>
</template>

<script>
import Toolbar from './components/Toolbar'
// import AppFooter from './components/AppFooter'

export default {
  components: { Toolbar },
  data: () => ({
    //
  })
}
</script>

<style scoped>
  .app{
    position: relative;
    color: black;
    font-size: 20px;
    min-height: 0vh;
  }
</style>

<style>
  #v-application--wrap{
    min-height: 0;
  }
  .content{
    padding: 0px;
  }
</style>
