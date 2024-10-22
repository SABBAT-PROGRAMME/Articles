<!-- tamplate -->
<template>
  <article>
    <header>
      <h3>{{ article.title.toUpperCase() }}</h3>
      <a href="#"
        >Date de publication : <i>{{ article.date_published }}</i></a
      >
      <br />
      Auteur : <b>{{ article.author }}</b>
    </header>
    <main>
      <h5>{{ article.summary }}</h5>
      <p>{{ article.content }}</p>
    </main>
    <footer>
      <a href="#"><u>category</u></a>
      <ul>
        <li>{{ article.category }}</li>
      </ul>
      <b>{{ article.tags }}</b
      ><br /><br />
      <a :href="article.image_url" target="_blank">Voir plus...</a>
    </footer>
  </article>

  <button @click="emit('next')">voir l'article suivant</button>
</template>

<!-- script -->
<script setup>
import { defineProps, ref } from "vue";

const props = defineProps({
  article: Object,
});

const next = ref(null);
const emit = defineEmits(["next"]);
</script>

<!-- style -->
<style></style>
