<script setup lang="ts">
import { ref } from "vue";
import Header from "@/components/Header.vue";
import Sidebar from "@/components/Sidebar.vue";

const active = ref(false)
</script>

<template>
  <div id="app">
    <Header @open-menu="active = true" />
    <Sidebar :active="active" @close-menu="active = false" />
    <RouterView />
  </div>
</template>

<style>
@font-face {
  font-family: gotham;
  src: url('/src/assets/fonts/GothamSSm-Book_Web.woff2');
  font-weight: normal;
}
  
@font-face {
  font-family: gotham;
  src: url('/src/assets/fonts/GothamSSm-Medium_Web.woff2');
  font-weight: bold;
}
  
:root {
  --white: #FEFEFE;
  --font: #393c41;
  --hover: rgba(0, 0, 0, .1);
}
  
*,
*::before,
*::after {
  font-family: gotham, sans-serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
  
html,
body,
#__nuxt,
#app {
  width: 100%;
  height: 100%;
}
</style>