<script setup>
import {ref} from "vue"

//pole primitivnich datovych typu (stirng, int, float, ...)
const poleZviratka = ref(["slon", "kachna", "slepice", "tulen", "zebra"]);

//pole objektu
const poleObjektZvire = ref([
    {
        jmeno: "slon",
        pocetNohou: 4
    },
    {
        jmeno: "orel",
        pocetNohou: 2
    },
    {
        jmeno: "had",
        pocetNohou: 0
    },
    {
        jmeno: "pavouk",
        pocetNohou: 8
    },
    {
        jmeno: "zebra",
        pocetNohou: 4
    }
]);

//iterovani vlastnosti 1 objektu
const lektor = ref({
    jmeno: "Tony",
    kurz: ["programovani", "javascript"],
    jeZivy: true,
    vyska: 162.5
});

//iterovat podle urciteho poctu
//v-for="cislo of 13"

</script>

<template>
    <h3>Direktiva v-for</h3>

    <ul>
        <li v-for="zvire of poleZviratka">{{ zvire }}</li>
    </ul>

    <hr>

    <table border="1px">
        <tr>
            <th>Jmeno</th>
            <th>Pocet nohou</th>
        </tr>

        <tr v-for="objektZvire of poleObjektZvire">
            <td>{{ objektZvire.jmeno }}</td>
            <td>{{ objektZvire.pocetNohou }}</td>
        </tr>

    </table>

    <hr>

    <p v-for="(hodnotaVlastnosti, vlastnost) in lektor">
        {{ vlastnost }}: {{ hodnotaVlastnosti }}
    </p>

    <hr>
    <!-- v-for zacina od 1 -->
    <h4 v-for="cislo of 5">Nadpis cislo {{ cislo }}</h4>


    <hr>
    <!-- pokud chceme cyklem v-for vypsat nekolik elementu a nechceme aby elementy byly uvnitr divu,tak pouzijeme element template -->

    <template v-for="cislo of 3">
        <h5>Kocka</h5>
        <p>cici</p>    
    </template>
    
    <!-- POZOR!!! nikdy nesmi byt na jednom elementu v-for a v-if -->
    <!-- <p v-for="" v-if=""></p> -->


</template>

<style scoped>
</style>