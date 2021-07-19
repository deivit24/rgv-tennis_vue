<template lang="pug">
v-card.mx-auto(max-width='500')
  v-toolbar(color="blue darken-4" dark)
    v-toolbar-title Contact Us Today
    v-spacer  
  v-card-text
    v-form(
      ref="form"
      v-model="valid"
      name="contact-speaker" 
      netlify 
      netlify-honeypot="bot-field" 
      lazy-validation
    )
      v-container
        v-row
          v-col(cols='12')
            v-text-field(v-model='form.name' name="name" :rules='nameRules' :counter='10' label='Name' required)
          v-col(cols='12')
            v-text-field(
              v-model='form.email' 
              email="email" 
              :rules='emailRules' 
              label='E-mail' 
              required
            )
          v-col(cols='12')
            v-textarea(
              rows="1",
              auto-grow
              v-model='form.message' 
              name="message" 
              :rules='messageRules' 
              :counter='200'
              label='Enter a message' 
              required
            )
          v-btn.ml-auto.mt-3(
            color="blue darken-4"
            class="mr-4"
            dark
            @click="handleSubmit"
          ) Submit
      v-alert(type="success" v-if="snackbar" :key="rerender").mt-5
        | {{text}}
        

</template>

<script>
import axios from "axios";
export default {
  name: "Form",
  data: () => ({
    valid: false,
    snackbar: false,
    text: "Message Successful!",
    timeout: 3000,
    rerender: 0,
    form: {
      name: "",
      email: "",
      message: "",
    },
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => v.length <= 20 || "Name must be less than 20 characters",
    ],
    messageRules: [
      (v) => !!v || "Message is required",
      (v) => v.length <= 200 || "Name must be less than 200 characters",
    ],
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+/.test(v) || "E-mail must be valid",
    ],
  }),
  methods: {
    resetForm() {
      this.form = {
        name: "",
        email: "",
        message: "",
      };
      this.$refs.form.resetValidation();
    },
    encode(data) {
      return Object.keys(data)
        .map(
          (key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`
        )
        .join("&");
    },
    handleSubmit() {
      try {
        const axiosConfig = {
          header: { "Content-Type": "application/x-www-form-urlencoded" },
        };

        axios.post(
          "/",
          this.encode({
            "form-name": "contact-speaker",
            ...this.form,
          }),
          axiosConfig
        );
        this.snackbar = true;
        this.text = "Message Successful!";
        this.rerender++;
        this.resetForm();
      } catch (error) {
        this.text = "Failed to send";
      }
    },
  },
};
</script>
