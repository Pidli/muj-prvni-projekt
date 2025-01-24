<script setup>
import { ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from "vue"
import LifecycleHookyChild from "./LifecycleHookyChild.vue";

//rodicovska componenta
console.log("vytvarim komponentu");

onBeforeMount(() => {
    console.log("parent komponenta se pripravuje k mountnuti");
});

onMounted(() => {
    console.log("parent komponenta byla mountnuta");
});

onBeforeUpdate(() => {
    console.log("parent komponeneta se pripravuje k prekresleni");
});

onUpdated(() => {
    console.log("parent komponeneta se prekreslila");
});

onBeforeUnmount(() => {
    console.log("parent komponeneta se pripravuje k unmountnuti");
});

onUnmounted(() => {
    console.log("parent komponeneta se unmountnula");
});


const zobrazeno = ref(true)
</script>

<template>
    <h3>Lifecycle Hooky</h3>

    <button @click="zobrazeno=!zobrazeno">Zobrazit/Skryt Child</button>
    <LifecycleHookyChild v-if="zobrazeno" />

</template>

<style scoped></style>