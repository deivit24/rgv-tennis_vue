<template lang="pug">
v-card.mx-auto(max-width='400')
  v-img.align-end(height='200px' :src="img")
    v-card-title {{title}}
  v-card-subtitle.pb-0
    | {{subtitle}}
  v-card-text.text--primary
    div {{text}}
  v-card-actions
    v-btn(color='orange' text)
      | Sign up
   


</template>

<script>
export default {
  name: "ProgramCard",
  props: {
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
