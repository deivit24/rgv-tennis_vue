<template lang="pug">
v-card.mx-auto(max-width='400')
  v-img.align-end(:height='height'  :src="src" dark)
    v-card-title( style="background:rgba(0, 0, 0, 0.5)") {{title}}
  v-card-subtitle.pb-0.mb-2
    | {{subtitle}}
  v-card-text().text--primary
    p {{text}}
  

  v-card-actions
    v-btn(color='orange' text)
      | Sign up
   


</template>

<script>
export default {
  name: "CoachCard",
  props: {
    height: {
      type: String,
      required: false,
      default: "200px",
    },
    title: {
      type: String,
      required: true,
    },
    subtitle: {
      type: String,
      required: true,
    },
    text: {
      type: String,
      required: true,
    },
    src: {
      type: String,
      default: "https://cdn.vuetifyjs.com/images/cards/cooking.png",
    },
  },
};
</script>
