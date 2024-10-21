<!-- Footer.vue -->
<template>
  <footer>
    <u>category</u>
    <ul>
      <li>{{ category }}</li>
    </ul>
    <b>{{ tags }}</b
    ><br />
    <a :href="imageUrl" target="_blank">Voir l'image</a>
  </footer>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  category: String,
  tags: String,
  imageUrl: String,
});
</script>

<style scoped>
/* Ajoute ton style ici */
</style>
