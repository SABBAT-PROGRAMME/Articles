<!-- Footer.vue -->
<template>
  <footer>
    <a href="#"> <u>category</u></a>
    <ul>
      <li>{{ category }}</li>
    </ul>
    <b>{{ tags }}</b
    ><br />
    <br />
    <a :href="imageUrl" target="_blank">Voir plus...</a>
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
