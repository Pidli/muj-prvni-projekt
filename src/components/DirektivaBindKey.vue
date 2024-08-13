<script setup>
import {ref} from "vue"

const poleZvirat = ref([
    {
        id: 15,
        jmeno: "pes"
    }, 
    {
        id: 4,
        jmeno: "kocka"
    },
    {
        id: 22,
        jmeno:"had"
    },
    {
        id: 1,
        jmeno: "kachna"
    },
    {
        id: 5,
        jmeno: "krava"
    }
]);

function seraditAbecedne() {
    poleZvirat.value.sort((zvireA, zvireB) => {
        if(zvireA.jmeno < zvireB.jmeno ) {
            return -1;
        }

        if(zvireA.jmeno > zvireB.jmeno) {
            return 1;
        }

        return 0;        
    });
}

</script>

<template>
    <h3>Direktiva v-bind (key)</h3>
    <ul>
        <li v-for="zvire of poleZvirat" :key="zvire.id">
            {{zvire.jmeno}}
            <input type="text" name="" id="">
        </li>
    </ul>

    <button @click="seraditAbecedne()">Seradit podle abecedy</button>
</template>

<style scoped>
</style>