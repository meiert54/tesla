<script setup lang="ts">
import { computed, useAttrs } from "vue";
import Section from "@/components/Section.vue";

const attrs = useAttrs()

const scrollingMode = computed(() => attrs.active ? { overflowY: 'hidden' } : { overflowY: 'scroll' })
</script>

<template>
    <main class="index-page" :style="scrollingMode">
        <Section :is-model="true" name="y" img="model-y.png" :ncap="true" />
        <Section :is-model="true" name="3" img="model-3.png" :ncap="true" />
        <Section :is-model="true" name="s" img="model-s.png" :ncap="false" />
        <Section :is-model="true" name="x" img="model-x.png" :ncap="false" />
        <Section :is-model="false" name="powerwall" img="powerwall.png" :ncap="false" />
        <Section :is-model="false" name="accessoires" img="accessoires.png" :ncap="false" />
    </main>
</template>