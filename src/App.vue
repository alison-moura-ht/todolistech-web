<template>
  <v-app>
    <app-navbar></app-navbar>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script setup>
import AppNavbar from "./components/AppNavbar.vue"
</script>

<script>
export default {
  name: 'App',
  data: () => ({
    
  }),
}
</script>
