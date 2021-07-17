<template lang="pug">

v-container(fluid).pa-0: v-card(flat color="#333" dark): v-row(no-gutters)
  v-col(cols=12 md=6).pa-5.d-flex.flex-column.justify-center.text-center
    p Contact 
    p Agustin Salazar
    p 956-571-6088
    p rgvtennisacademy@hotmail.com
  v-col(cols=12 md=6).pa-5.d-flex.flex-column.justify-center.text-center
    iframe( src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d5061.708440447343!2d-98.2426512942601!3d26.223718481961022!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8665a0cfb2c916f5%3A0x19f3e219c98f05d2!2sMcAllen%20High%20School!5e0!3m2!1sen!2sus!4v1566772520644!5m2!1sen!2sus" width="600" height="250" frameborder="0" style="border:0;" allowfullscreen="").ml-auto.mr-auto
</template>

<script>
export default {
  name: "Footer",
};
</script>
