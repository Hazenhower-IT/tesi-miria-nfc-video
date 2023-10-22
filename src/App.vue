<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Header from "./components/Header.vue"
import Footer from "./components/Footer.vue"
//#3c3b3a
</script>

<template>
  <Header />

  <RouterView />

  <Footer />
</template>

<style >
*, body{
  background: #000;
}
</style>
