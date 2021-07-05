<template lang="pug">
v-app
  NavBar
  main
    router-view
  Footer
</template>

<script>
import NavBar from "./components/NavBar.vue";
import Footer from "./components/Footer";
export default {
  name: "App",
  components: {
    NavBar,
    Footer,
  },
  data: () => ({
    //
  }),
};
</script>
