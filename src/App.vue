<template>
<HelloWorld></HelloWorld>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
export default {
  name: "App",

  components: {
    HelloWorld,
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
