<template>
    <v-container class="contact">
      <h1>Want to work together?</h1>
      <v-layout row>
        <br>
        <br>
        <br>

            <ContactForm/>


      </v-layout>
  
    </v-container>
  </template>
  
  <script>
  import ContactForm from '../components/ContactForm.vue';
  export default {
    name: 'ContactView',
    components: {
      ContactForm
    
    }
  }
  
  </script>
  
  <style scoped>
  h1 {
    margin-top: 10vh;
    /* margin-bottom: 2vh; */
    font-size: 4rem;
    text-align: center;
  }

  h2 {
    left: 25%;
    position: absolute;
  }


  
  </style>
  