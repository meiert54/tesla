<script setup lang="ts">
import Section from "@/components/Section.vue";
</script>

<template>
    <main class="index-page">
        <Section :is-model="true" name="y" :ncap="true" />
        <Section :is-model="true" name="3" :ncap="true" />
        <Section :is-model="true" name="s" :ncap="false" />
        <Section :is-model="true" name="x" :ncap="false" />
        <Section :is-model="false" name="powerwall" :ncap="false" />
        <Section :is-model="false" name="accessoires" :ncap="false" />
    </main>
</template>