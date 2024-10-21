<!-- template -->
<template>
  <br />

  <!-- Boucle pour afficher les articles -->
  <div v-for="(article, index) in myArticles.articles" :key="index">
    <article>
      <!-- Header -->

      <Header
        :id="index + 1"
        :title="article.title"
        :author="article.author"
        :datePublished="article.date_published"
      />
      <!-- Body -->
      <Body :summary="article.summary" :content="article.content" />
      <!-- Footer -->
      <Footer
        :category="article.category"
        :tags="article.tags"
        :imageUrl="article.image_url"
      />
    </article>
    <button disabled>Voir l'article suivant</button>
    <br />
    <br />
  </div>

  <!-- Autre contenu -->
</template>

<!-- script -->
<script setup>
import { defineProps } from "vue";
import Header from "./Header.vue";
import Body from "./Body.vue";
import Footer from "./Footer.vue";

// Définir les props pour recevoir les données
const props = defineProps({
  myArticles: Object,
});
</script>

<!-- style -->

<style>
button {
  margin-left: auto;
  display: block;
}
</style>
