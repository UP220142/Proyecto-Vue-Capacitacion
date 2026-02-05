<script setup>
defineProps(["inicio", "fin", "totalPosts"]);

const emit = defineEmits(['next', 'prev', 'totalPosts']);
</script>


<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button @click="emit('prev')" type="button" class="btn btn-outline-primary" :disabled="inicio <= 0">Previous {{ inicio }}</button>
        <button @click="emit('next')" type="button" class="btn btn-outline-primary" :disabled="fin >= totalPosts">Next {{ fin }}</button>
    </div>
</template>
