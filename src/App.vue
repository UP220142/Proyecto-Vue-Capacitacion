<script setup>
import { ref } from 'vue';
import { computed } from 'vue';

import BlogPost from './components/BlogPost.vue'
import PaginatePost from './components/PaginatePost.vue'
import LoadingSpiner from './components/LoadingSpiner.vue'

const posts = ref([]);
const postXpage = 10;
const inicio = ref(0)
const fin = ref(postXpage)
const loading = ref(true);

const favorito = ref("");

const totalPosts = computed(() => posts.value.length);

const cambiarFavorito = (title) => {
  favorito.value = title;
};

const next = () => {
  inicio.value += postXpage
  fin.value += postXpage
};
const prev = () => {
  inicio.value -= postXpage
  fin.value -= postXpage
};

fetch("https://jsonplaceholder.typicode.com/posts")
  .then((res) => res.json())
  .then((data) => {
    posts.value = data;

  })
  .finally(() => {
    loading.value = false;
  });
</script>

<template>
  <LoadingSpiner v-if="loading" />
  <div class="container" v-else>
    <h1>APP</h1>
    <h2>Mi Post Favorito: {{ favorito }}</h2>

    <PaginatePost @next="next" @prev="prev" :inicio="inicio" :fin="fin" :totalPosts="totalPosts" class="mb-2" />

    <BlogPost v-for="post in posts.slice(inicio, fin)" :key="post.id" :title="post.title" :id="post.id"
      :body="post.body" @cambiarFavoritoNombre="cambiarFavorito" class="mb-2" />
  </div>
</template>
