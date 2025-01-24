<script setup>
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from "vue"

//child componenta

const pocitadlo = ref(0);

onBeforeMount(() => {
    console.log("child komponenta se pripravuje k mountnuti");
});

onMounted(() => {
    console.log("child komponenta byla mountnuta");
});

onBeforeUpdate(() => {
    console.log("child komponeneta se pripravuje k prekresleni");
});

onUpdated(() => {
    console.log("child komponeneta se prekreslila");
});

onBeforeUnmount(() => {
    console.log("child komponeneta se pripravuje k unmountnuti");
});

onUnmounted(() => {
    console.log("child komponeneta se unmountnula");
});

</script>

<template>
    <h4>Pocitadlo</h4>

    <p>{{ pocitadlo }}</p>
    <button @click="pocitadlo++">plus</button>
    <button @click="pocitadlo--">minus</button>

</template>


<style scoped></style>