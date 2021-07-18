<template lang="pug">
main
  v-parallax(dark, src='../assets/programs.jpg' height="1000")
    v-container
      v-row(align='center', justify='center')
        v-col.text-center(cols='12' )
          h1.text-h1.font-weight-bold.mb-4
            | Programs for all levels
  v-container
    v-row(style="margin: 200px 0px")
      v-col(cols=12).text-center
        h1.font-weight-thin.mb-3 Programs and Schedule
      v-col(
        cols=12 md=4 v-for="card in programCards"
        )
        ProgramCard(
          :title="card.title", 
          :subtitle="card.subtitle", 
          :time="card.time", 
          :price="card.price",
          :src="card.src",
          :key="card.title"
        )

</template>

<script>
import QuickStart from "../assets/quickstart.jpg";
import ProgramCard from "../components/ProgramCard.vue";
import Inter from "../assets/inter.jpg";
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
        subtitle: "Group Meets: Mon & Wed or Tues & Thurs",
        time: "5:00pm – 6:00pm",
        price: "2 Days a Week $50per Month",
        src: QuickStart,
      },
      {
        title: "Youth/Intermediate: Ages 8 - 11",
        subtitle: "Group Meets: Monday -Thursday",
        time: "Time: 5:00pm –6:30pm",
        price: "2 Days a Week $75per Month 3 – 4 Days a Week $100per Month",
        src: Inter,
      },
      {
        title: "Intermediate Advance: All Ages",
        subtitle: "Group Meets: Monday – Thursday",
        time: "Time: 6:00pm – 8:00pm & 5:00pm – 6:30pm on Friday",
        price: "2 Days a Week $100per Month 3 – 4 Days a Week $125per Month",
        src: SignUp,
      },
    ],
  }),
};
</script>

<style scoped>
#program {
  height: 100vh;
}
</style>
