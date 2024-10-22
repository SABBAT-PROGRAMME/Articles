<!-- Header.vue -->
<template>
  <header>
    <h3>{{ title.toUpperCase() }}</h3>
    <p>
      Auteur : <i>{{ author }}</i>
    </p>
    <a href="#">
      Date de publication : <i>{{ datePublished }}</i>
    </a>
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
