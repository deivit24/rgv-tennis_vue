<template lang="pug">
main
  v-parallax(dark, src='../assets/programs.jpg' height="730")
    v-container
      v-row(align='center', justify='center')
        v-col.text-center(cols='12' style="background:rgba(0, 0, 0, 0.4)")
          h1.text-h1.font-weight-normal.mb-4
            | RGV offers programs for all levels
  v-container: v-row.mt-5
    v-col(cols=12 md=4 v-for="card in programCards")
      ProgramCard(
        :title="card.title", 
        :subtitle="card.subtitle", 
        :text="card.text", 
        :src="card.src",
        :key="card.text"
      )
       
      
  
</template>

<script>
import ProgramImg from "../assets/programs.jpg";
import ProgramCard from "../components/ProgramCard.vue";
import Logo from "../assets/logo2.png";
import SignUp from "../assets/tourn.jpg";
export default {
  name: "Programs",
  components: {
    ProgramCard,
  },
  data: () => ({
    programCards: [
      {
        title: "Beginners: Quick-Start Ages 4 - 7",
        subtitle: "Programs",
        text: "RGV Tennis Academy has a diverse set of programs for all ages and levels. We take commit ourselves to every student, regardless of level.",
        src: ProgramImg,
      },
      {
        title: "Youth/Intermediate: Ages 8 - 11",
        subtitle: "About",
        text: "Learn more about the history RGV Tennis Academy and their coaches",
        src: Logo,
      },
      {
        title: "Intermediate Advance: All Ages",
        subtitle: "Sign Up",
        text: "Go to our inteactive form to sign up and contact us. We would love ot hear from you!",
        src: SignUp,
      },
    ],
  }),
};
</script>
