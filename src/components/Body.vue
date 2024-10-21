<!-- Body.vue -->
<template>
  <section>
    <h5>{{ summary }}</h5>
    <p>{{ content }}</p>
  </section>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  summary: String,
  content: String,
});
</script>

<style scoped>
/* Ajoute ton style ici */
</style>
