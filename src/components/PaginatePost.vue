<script setup>
const emit = defineEmits(['next', 'prev']);

const activarSiguiente = () => {
    emit('next');
};
const activarAnterior = () => {
    emit('prev');
};
</script>


<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button @click="activarAnterior" type="button" class="btn btn-outline-primary">Previous</button>
        <button @click="activarSiguiente" type="button" class="btn btn-outline-primary">Next</button>
    </div>
</template>
