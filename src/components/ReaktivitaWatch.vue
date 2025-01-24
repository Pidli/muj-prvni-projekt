<script setup>
import {ref, watch} from "vue"

//computed reaguje na zmeny reaktivnich vlastnosti
//computed by mela vzdy jen vracet novou hodnotu
//computed muze reaktivni promenne jenom cist nesmi je menit

//watcher stejne jako computed reaguje na zmeny reaktivnich promennych
//watcher muze spoustet "side effecty"
//watcher zna starou i novou hodnotu zavisle reaktivni promenne

const cislo = ref(0);

setInterval(() => {
    cislo.value = Math.floor(Math.random() * 10);
}, 3000);


const poleZaznamu = ref([]);

//prijima 2 parametry
//1) sledovana promenna
//2) arrow funkce, ktera se spusti pokud se sledovana promenna zmeni
watch(cislo, (novaHodnota, staraHodnota) => {
    if (poleZaznamu.value.length >= 5) {
        poleZaznamu.value = [];
    }

    poleZaznamu.value.push({
        hodnota: novaHodnota,
        zmena: novaHodnota > staraHodnota ? "rust" : "pokles"
    });
}, { immediate: true });

</script>

<template>
    <h3>Reaktivita watch</h3>
    <p>Aktualni cislo: {{ cislo }}</p>
    <div class="container">
        <ul>
            <li v-for="zaznam of poleZaznamu">{{ zaznam }}</li>
        </ul>
    </div>
</template>

<style scoped>
    .container {
        min-height: 13rem;
    }
</style>