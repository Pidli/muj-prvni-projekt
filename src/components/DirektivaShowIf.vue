<script setup>
import {ref, computed} from "vue"

const zobrazeno = ref(false);
const computedTextTlacitka = computed(() => {
    if (zobrazeno.value) {
        return "Skryt";
    }else{
        return "Zobrazit";
    }
});


const pocetKopecku = ref(0);


const paragrafyZobrazeno = ref(false);
</script>

<template>
    <h3>Direktiva v-show a v-if</h3>
    <p v-show="zobrazeno">Toto je tajny text.</p>
    <button @click="zobrazeno = !zobrazeno">{{computedTextTlacitka}} text</button>

    <p>Kolik chcte kopecku?</p>
    <p>Aktualni pocet: {{ pocetKopecku }}</p>
    <button @click="pocetKopecku++">Pridat</button>
    <button @click="pocetKopecku--">Odebrat</button>
    <p v-if="pocetKopecku > 10">Toto je az moc!!!</p>
    <p v-else-if="pocetKopecku > 5">Toto je trochu hodne!!!</p>
    <p v-else-if="pocetKopecku > 3">Toto je idealni pocet!!!</p>
    <p v-else>Toto je moc malo!!!</p>

    <button @click="paragrafyZobrazeno = !paragrafyZobrazeno">Zobrazit/skryt paragrafy</button>
    <template v-if="paragrafyZobrazeno">
        <p>haha</p>
        <p>hehe</p>
    </template>

</template>

<style scoped></style>