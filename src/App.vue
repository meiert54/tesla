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