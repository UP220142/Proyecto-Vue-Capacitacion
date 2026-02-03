<script setup>
defineProps({
  title: String,
  id: Number,
  body: {
    type: String,
    default: "No hay descripcion"
  }
})
</script>

<template>
  <div class="card">
    <div class="card-body">
      <h5 class="card-title">{{ id }} - {{ title }}</h5>
      <p>{{ body }}</p>
    </div>
  </div>
</template>