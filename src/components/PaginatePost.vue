<script setup>
const emit = defineEmits(['next', 'prev']);

const activarSiguiente = () => {
    console.log("Me diste el siguiente");
    emit('next');
};
const activarAnterior = () => {
    console.log("Me diste el anterior");
    emit('prev');
};
</script>


<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button @click="activarAnterior" type="button" class="btn btn-outline-primary">Previous</button>
        <button @click="activarSiguiente" type="button" class="btn btn-outline-primary">Next</button>
    </div>
</template>
