<template lang="pug">
main
  v-parallax(dark, src='../assets/cover.jpg' height="730")
    v-container: v-row(align='center', justify='center')
      v-col.text-center(cols='12' md='6' style="background:rgba(0, 0, 0, 0.4)")
        h1.text-h1.font-weight-thin.mb-4
          | Welcome
        h4.text-h3.font-weight-normal.mb-4
          | To RGV Tennis Academy
        h4.text-h4.font-weight-normal.mb-4
          | Start Riping it Today!
      v-col.text-center(cols='12' md='6')
        Form
  v-container: v-row
    v-col(cols=12 v-for="card in cards")
      HomeCard(
        :title="card.title", 
        :subtitle="card.subtitle", 
        :text="card.text", 
        :src="card.src",
        :to="card.to",
        :first="card.first"
      )
</template>

<script>
import HomeCard from "../components/HomeCard";
import Form from "../components/Form.vue";
import ProgramImg from "../assets/ten2.png";
import Logo from "../assets/logo2.png";
import SignUp from "../assets/tourn.jpg";

export default {
  name: "Home",
  components: {
    HomeCard,
    Form,
  },
  data: () => ({
    cards: [
      {
        title: "view our programs",
        subtitle: "Programs",
        text: "RGV Tennis Academy has a diverse set of programs for all ages and levels. We take commit ourselves to every student, regardless of level.",
        src: ProgramImg,
        to: "/programs",
        first: false,
      },
      {
        title: "About RGV",
        subtitle: "About",
        text: "Learn more about the history RGV Tennis Academy and their coaches",
        src: Logo,
        to: "/coaches",
        first: false,
      },
      {
        title: "Sign Up Today",
        subtitle: "Sign Up",
        text: "Go to our inteactive form to sign up and contact us. We would love ot hear from you!",
        src: SignUp,
        to: "/contact",
        first: false,
      },
    ],
  }),
};
</script>
