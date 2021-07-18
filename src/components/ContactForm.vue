<template lang="pug">
v-card.mx-auto(max-width='500')
  v-toolbar(color="blue darken-4" dark)
    v-toolbar-title Contact Us Today
    v-spacer  
  v-card-text
    v-form(ref="form"
    v-model="valid"
    lazy-validation)
      v-container
        v-row
          v-col(cols='12')
            v-text-field(v-model='name' name="name" :rules='nameRules' :counter='10' label='Name' required)
          v-col(cols='12')
            v-text-field(
              v-model='email' 
              email="email" 
              :rules='emailRules' 
              label='E-mail' 
              required
            )
          v-col(cols='12')
            v-textarea(
              v-model='message' 
              name="message" 
              :rules='messageRules' 
              :counter='200'
              label='Enter a message' 
              required
            )
          v-btn.ml-auto.mt-3(
            :disabled="!valid"
            color="blue darken-4"
            class="mr-4"
            dark
          ) Submit
    

</template>

<script>
export default {
  name: "ContactForm",
  data: () => ({
    valid: false,
    name: "",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => v.length <= 10 || "Name must be less than 10 characters",
    ],
    email: "",
    message: "",
    messageRules: [
      (v) => !!v || "Message is required",
      (v) => v.length <= 200 || "Name must be less than 200 characters",
    ],
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+/.test(v) || "E-mail must be valid",
    ],
  }),
};
</script>
