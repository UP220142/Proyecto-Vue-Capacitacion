<script setup>
import ButtonCounter from './components/ButtonCounter.vue'
import BlogPost from './components/BlogPost.vue'
import { ref } from 'vue';

const posts = ref([
  { id: 1, title: 'Post 1', body: 'description 1' },
  { id: 2, title: 'Post 2', body: 'description 2' },
  { id: 3, title: 'Post 3', body: 'description 3' },
  { id: 4, title: 'Post 4' },
]);

const favorito = ref("");

const cambiarFavorito = (title) => {
  favorito.value = title;
};
</script>

<template>
  <div class="container">
    <h1>APP</h1>
    <h2>Mi Post Favorito: {{ favorito }}</h2>
    
    <BlogPost v-for="post in posts" :key="post.id" :title="post.title" :id="post.id" :body="post.body"
      @cambiarFavoritoNombre="cambiarFavorito" />
  </div>
</template>
