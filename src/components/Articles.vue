<!-- template -->
<template>
  <h1>{{ myArticles.titre }}</h1>
  <Card :article="article" v-if="myArticles" @next="nextArticle" />
  <!-- Autre contenu -->
</template>

<!-- script -->
<script setup>
import { computed, defineProps, ref } from "vue";
import Card from "./Card.vue";

// Définir les props pour recevoir les données
const props = defineProps({
  myArticles: Object,
});

const step = ref(0);
const article = computed(() => props.myArticles.articles[step.value]);

// Lire l'article suivant
const next = ref(props.myArticles.articles.map(() => null));
const nextArticle = () => {
  step.value++;

  if (step.value >= props.myArticles.articles.length) {
    step.value = 0;
  }
};
</script>

<!-- style -->

<style>
button {
  margin-left: auto;
  display: block;
}
</style>
