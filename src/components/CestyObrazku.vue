<script setup>
import {ref} from "vue"

import cestaKObrazkuPejska from "@/assets/svg/dog.svg";


const cestaKObrazku = ref('');
function nactiObrazek() {
    cestaKObrazku.value = cestaKObrazkuPejska;
}

const dynamickaCesta = ref('');
function zjistiCestu(argZvire) {
    const sestavenaCesta = new URL(`../assets/svg/${argZvire}.svg`, import.meta.url).href;
    return sestavenaCesta;
}
function vyberZvire(argZvire) {
    dynamickaCesta.value = zjistiCestu(argZvire);
}

</script>

<template>
    <h3>Cesty obrazku</h3>
    <p>A) Musi obrazek mit pevny nazev nebo originalni kvalitu? (public)</p>
    <img src="/svg/bull.svg" alt="">
    <p>B) Pouziva vas projekt bundler Webpack? (require)</p>
    <p>C) Pokud vas projekt pouziva bundler Vite: Je src elementu img staticky? (../ nebo @/)</p>
    <img src="../assets/svg/cat.svg" alt="">
    <img src="@/assets/svg/cow.svg" alt="">
    <p>D) Je src obrazku dynamicke? (import)</p>
    <button @click="nactiObrazek()">Nacist obrazek</button>
    <img :src="cestaKObrazku" alt="">
    <p>E) Neznate dopredu konkretni url obrazku? (new URL)</p>
    <button @click="vyberZvire('parrot')">Nacist papouska</button>
    <button @click="vyberZvire('sheep')">Nacist ovecku</button>
    <img :src="dynamickaCesta" alt="">
    <p>F) Bonus: Potrebujete naimportovat celou sadu obrazku? (glob)</p>
</template>

<style scoped>
img {
    width: 5rem;
}
</style>