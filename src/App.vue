<template>
  <v-app>
      <Navbar/>
    <v-content class=" mb-4">
      <router-view></router-view>
    </v-content>
      <BottomNavbar/>
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
import BottomNavbar from '@/components/BottomNavbar.vue'

export default {
  name: 'App',
  components: { Navbar, BottomNavbar },
  data: () => ({
    //
  }),
};
</script>

<style>
  #app {
    background-color:#1b1d1f;  
  }
</style>