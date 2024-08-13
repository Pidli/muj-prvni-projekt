<script setup>
import { ref } from "vue"

//reaktivni promenna/state
//state vytvorime funkci ref()
//do kulatych zavorek napisete vychozi hodnotu promenne
const cas = ref(1);
setInterval(() => {
    //kdykoliv budeme potrebovat pracovat s hodnotou nejakeho state (ref), tak musime pouzit vlasnost value
    //console.log(cas.value);
    cas.value += 1;
}, 1000);

</script>

<template>
    <h3>Reaktivita ref</h3>
    <!-- mustache zapis {{  }} -->
    <p>Cas straveny na strance: {{ cas }} s</p>
</template>

<style scoped>
</style>