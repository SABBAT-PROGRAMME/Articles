<!-- tamplate -->
<template>
  <article>
    <header>
      <Header
        :article="article"
        :id="article.id"
        :title="article.title"
        :author="article.author"
        :datePublished="article.date_published"
      />
    </header>
    <main>
      <Body :summary="article.summary" :content="article.content" />
    </main>
    <footer>
      <Footer
        :category="article.category"
        :tags="article.tags"
        :imageUrl="article.imageUrl"
      />
    </footer>
  </article>

  <button @click="emit('next')">voir l'article suivant</button>
</template>

<!-- script -->
<script setup>
import { defineProps, ref } from "vue";
import Header from "./Header.vue";
import Body from "./Body.vue";
import Footer from "./Footer.vue";

const props = defineProps({
  article: Object,
});

const next = ref(null);
const emit = defineEmits(["next"]);
</script>

<!-- style -->
<style></style>
