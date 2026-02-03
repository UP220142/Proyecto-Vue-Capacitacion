<script setup>
import ButtonCounter from './components/ButtonCounter.vue'
import BlogPost from './components/BlogPost.vue'
</script>

<template>
  <div class="container">
    <h1>APP</h1>
    <ButtonCounter />
    <button-counter></button-counter>
    
    <BlogPost title="Post 1" id="1" body="description 1" colorText="primary" />
    <BlogPost title="Post 2" id="2" body="description 2" colorText="secondary"/>
    <BlogPost title="Post 3" id="3" body="description 3" colorText="success"/>
    <BlogPost title="Post 4" id="4" body="description 4" colorText="primary"/>
  </div>
</template>

