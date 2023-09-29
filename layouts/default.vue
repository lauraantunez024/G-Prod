<template>
  <!-- <div> -->
  <v-app dark>
   
    <v-app-bar
      :clipped-left="clipped"
      
      app
    >
   
      <v-btn to="/" link>{{ title }}</v-btn>
      <v-spacer />
      <v-btn :to="'/about'" link>About</v-btn>
      <v-btn :to="'/directory'" link>Portfolio</v-btn>
      <v-btn :to="'/resume'" link>Resume</v-btn>
  
    </v-app-bar>
 
        <Nuxt />
        <v-spacer/>
      <slot/>
      <v-spacer/>
    </v-app>

</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-cat',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-video-vintage',
          title: 'Video Projects',
          to: '/videos'
        },
        {
          icon: 'mdi-audio-input-stereo-minijack',
          title: 'Audio Projects',
          to: '/audio'
        },
        {
          icon: 'mdi-cellphone',
          title: 'Contact Me',
          to: '/contact'
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Grace Rolfe"
    }
  }
}
</script>
<style scoped>
.v-toolbar__title {
  margin-left: 45vw;
  font-size: 2rem;
}


</style>