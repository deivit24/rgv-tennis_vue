<template lang="pug">
v-card.mx-auto(max-width='900px', flat).my-10
  v-row
    v-col(cols=12 md=6).d-flex.flex-column.justify-center.alighn-center
     
      .text-h5.font-weight-normal.overline.mb-4
        | {{title}}
      
      p {{text}}
      v-card-actions
        v-btn(outlined
        color="primary"
          rounded
          text
          :to="to") Explore
    v-col(cols=12 md=6 :class="first ? 'order-first': ''")
      v-img(:src="src")

</template>

<script>
export default {
  name: "HomeCard",
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
    to: {
      type: String,
      default: "/",
    },
    first: {
      type: Boolean,
      default: false,
    },
    src: {
      type: String,
      default: "https://cdn.vuetifyjs.com/images/cards/cooking.png",
    },
  },
};
</script>
