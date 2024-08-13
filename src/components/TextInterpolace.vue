<script setup>
import {ref} from "vue";

//ulozime do reaktivni vlastnosti nahodne cislo mezi 0(inclusivni) a 1
const nahodneCislo = ref(Math.random());
//kazde 2 sekundy vygenerovat nahodne cislo
setInterval(() => {
    nahodneCislo.value = Math.random();
}, 2000);

function pozdrav() {
    return "Ahoj";
}

const jmenoTucneHtml = "<strong>Tony</strong>";

</script>

<template>
    <h3>Text interpolace</h3>
    <!-- mustache -->
    <!-- {{  }} se snazi vzdy vypsat hodnotu jako text -->
    <p>Reaktivni vlastnost/promenna: {{ nahodneCislo }}</p>
    <p>Vyraz: {{ nahodneCislo * 10 }}</p>
    <p>Funkce: {{ pozdrav() }}</p>
    <p>Html string se vypise jako plain text: {{ jmenoTucneHtml }}</p>
    <p>Globalni promenna: {{ Date() }}</p>
    <!-- nemuzeme uvnitr  {{  }} pouzit if else -->
    <!-- <p>If else: {{ if(nahodneCislo > 0.5) {"Ahoj"} else {"Cau"} }}</p> -->
    <!-- existuje ale alternativa, ktera je povolena -->
    <p>Ternarni operator: {{ (nahodneCislo > 0.5) ? "Ahoj!" : "Cau!" }}</p>
</template>