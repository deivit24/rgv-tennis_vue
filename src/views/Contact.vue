<template lang="pug">
  #contact
    ContactForm
</template>

<script>
import ContactForm from "../components/ContactForm.vue";
export default {
  name: "Contact",
  components: {
    ContactForm,
  },
};
</script>

<style scoped>
#contact {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
