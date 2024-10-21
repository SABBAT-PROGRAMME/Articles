<!-- Header.vue -->
<template>
  <header>
    <h3>{{ id }}. {{ title }}</h3>
    <p>
      Auteur : <i>{{ author }}</i>
    </p>
    <p>
      Date de publication : <i>{{ datePublished }}</i>
    </p>
  </header>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  id: Number,
  title: String,
  author: String,
  datePublished: String,
});
</script>

<style scoped>
/* Ajoute ton style ici */
</style>
