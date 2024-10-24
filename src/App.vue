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
    <div class="card" v-if="state === 'error'">
      <article class="error">
        <header><h1>Oup's error</h1></header>
        <main><h2>404</h2></main>
        <footer><h2>Page Not Found !</h2></footer>
      </article>
    </div>
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

<!-- style -->

<style>
.card {
  justify-content: center;
  align-items: center;
  color: red;
}
.error {
  color: red;
  text-align: center;
}
</style>
