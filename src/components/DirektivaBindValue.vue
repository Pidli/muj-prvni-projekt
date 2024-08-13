<script setup>
import { ref } from "vue"

const vaseBarva = ref();
const kodProduktu = ref();
const poleProduktu = ref([
    {id: "1a5t7", jmeno: "hrnek", cena: 150},
    {id: "8ee21", jmeno: "mobil", cena: 10000},
    {id: "rt7g5", jmeno: "tricko", cena: 300}
]);
const objektProduktu = ref(); 
const mujCheckbox = ref(); 

</script>

<template>
    <h3>Direktiva v-bind (value)</h3>

    <!-- vetsinou staci staticke value atributy -->
    <div>
        <p>Vase barva: {{ vaseBarva }}</p>
        <select v-model="vaseBarva">
            <option disabled value="">Vyberte</option>
            <option value="blue">Modra</option>
            <option value="red">Cervena</option>
            <option value="green">Zelena</option>
        </select>
    </div>

    <!-- pokud pouzijmeme dynamicke value, tak se staticke value zaignoruje -->
    <hr>
    <div>
        <p>Kod produktu: {{ kodProduktu }}</p>
        <select v-model="kodProduktu">
            <option disabled value="">Vyberte</option>
            <option
                v-for="produkt of poleProduktu"
                :key="produkt.id"
                :value="produkt.id"
            >
                {{ produkt.jmeno }}
            </option>
        </select>
    </div>


    <!-- staticke html value vzdy vraci string -->
    <!-- dynamicke html :value muze byt jakykoliv datovy typ -->
    <hr>
    <div>
        <p>Objekt produktu: {{ objektProduktu }}</p>
        <select v-model="objektProduktu">
            <option disabled value="">Vyberte</option>
            <option
                v-for="produkt of poleProduktu"
                :key="produkt.id"
                :value="produkt"
            >
                {{ produkt.jmeno }}
            </option>
        </select>
    </div>


    <!-- checkbox ma specialni true-value a false-value -->
    <hr>
    <div>
        <p>Muj checkbox: {{ mujCheckbox }}</p>
        <input
            type="checkbox"
            v-model="mujCheckbox"
            true-value="ano"
            false-value="ne"
        >
    </div>
    
</template>

<style scoped></style>