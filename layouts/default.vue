<template>
  <!-- <div> -->
  <v-app dark>
    <!-- <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          link
          
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->
    <v-app-bar
      :clipped-left="clipped"
      
      app
    >
      <!-- <v-app-bar-nav-icon @click.stop="drawer = !drawer" /> -->
   
      <v-btn to="/" link>{{ title }}</v-btn>
      <v-spacer />
      <v-spacer />
      <v-spacer />
      <v-spacer />
      <v-spacer />
      <v-spacer />
      <v-spacer />
      <v-btn>About</v-btn>
      <v-btn :to="'/directory'" link>Portfolio</v-btn>
      <v-btn :to="'/videos'" link>Resume</v-btn>
  
    </v-app-bar>
 
        <Nuxt />
      <slot/>
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