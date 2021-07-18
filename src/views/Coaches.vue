<template lang="pug">
main
  v-container
    v-row(style="margin: 250px 0px")
      v-col(cols=12).text-center
        h1.font-weight-thin.mb-3 Meet the coaches
      v-col(
        cols=12 md=6 v-for="card in coachCards"
        )
        CoachCard(
          :title="card.title", 
          :subtitle="card.subtitle", 
          :text="card.text", 
          :src="card.src",
          height="400px"
          :key="card.title"
        )

</template>

<script>
import CoachCard from "../components/CoachCard.vue";

export default {
  name: "Coaches",
  components: {
    CoachCard,
  },
  data: () => ({
    coachCards: [
      {
        title: "Agustin Salazar",
        subtitle: "Academy Director",
        text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        src: "https://png.pngitem.com/pimgs/s/506-5067022_sweet-shap-profile-placeholder-hd-png-download.png",
      },
      {
        title: "Alfonso Rodriguez",
        subtitle: "Head Coach",
        text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        src: "https://png.pngitem.com/pimgs/s/506-5067022_sweet-shap-profile-placeholder-hd-png-download.png",
      },
    ],
  }),
};
</script>

<style scoped>
#coach {
  height: 100vh;
}
</style>
