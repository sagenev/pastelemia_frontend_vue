<template>
  <v-app id="inspire">
    
    <HeaderSiderMenu></HeaderSiderMenu>

    <v-main>
      <v-container
        class="fill-height"
        fluid
      >
        <v-row
          align="center"
          justify="center"
        >
          <v-col class="shrink">
          <h2>HOLA</h2>
          </v-col>
        </v-row>
      </v-container>
    </v-main>

  <Footer></Footer>
    
  </v-app>
</template>

<script>
import HeaderSiderMenu from './components/dashboard/HeaderSiderMenu.vue'
import Footer from './components/dashboard/Footer.vue'
export default {
  name: "App",

  components: {
    HeaderSiderMenu,
    Footer
  },
  props: {
    source: String
  },
  data: () => ({
 
  }),
  created () {
      this.$vuetify.theme.dark = true
    }
};
</script>