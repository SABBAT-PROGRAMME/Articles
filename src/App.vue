<!-- template -->
<template>
  <div class="container">
    <div v-if="state === 'loading'">Chargement...</div>
    <div v-if="state === 'success'">
      <div class="card">
        <!-- Passer directement les données via props -->
        <Articles :myArticles="articlesloccal" v-if="articlesloccal" />
      </div>
    </div>
    <div v-if="state === 'error'">Error 404 une erreur est survenue !</div>
  </div>
</template>

<!-- script -->
<script setup>
import { onMounted, ref } from "vue";
import Articles from "./components/Articles.vue";

// Référence pour stocker les articles localement
const articlesloccal = ref({});
const state = ref("loading");

onMounted(() => {
  fetch("./data.json")
    .then((response) => {
      if (response.ok) {
        return response.json();
      } else {
        throw new Error("Une erreur est survenue");
      }
    })
    .then((data) => {
      articlesloccal.value = data; // Stocker toutes les données
      state.value = "success";
    })
    .catch((error) => {
      console.error(error);
      state.value = "error";
    });
});
</script>
