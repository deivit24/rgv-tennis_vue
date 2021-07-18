<template lang="pug">
v-app#app
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

<style>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@100;400;700&display=swap");

body {
  font-family: "Noto Sans JP", sans-serif;
}
</style>
