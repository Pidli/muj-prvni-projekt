<script setup>
import {ref} from "vue"

const objektStyle = ref({
    borderRadius: "50%",
    backgroundColor: "pink"
});
function zmenRadius(argRadius) {
    objektStyle.value.borderRadius = argRadius + '%'; //stary zapis vanilla JS
    objektStyle.value.borderRadius = `${argRadius}%`; //novy zapis vanilla JS
}


const objektStyle2 = ref({
    backgroundColor: 'aqua'
});
const poleObjektuStyle = ref([objektStyle.value, objektStyle2.value]);


const barvaKolecka = ref('gold');
function zmenBarvu() {
    barvaKolecka.value = 'red';
}
</script>

<template>
    <h3>Direktiva v-bind (style + CSS)</h3>
    <h4>Objekt</h4>
    <button @click="zmenRadius(10)">Zmen radius 10</button>
    <button @click="zmenRadius(20)">Zmen radius 20</button>
    <button @click="zmenRadius(50)">Zmen radius 50</button>
    <div style="width: 7rem; height: 7rem; background-color: khaki;" v-bind:style="objektStyle"></div>

    <hr>
    <h4>Pole objektu</h4>
    <div style="width: 7rem; height: 7rem; background-color: khaki;" :style="poleObjektuStyle"></div>

    <hr>
    <h4>v-bind v CSS</h4>
    <div class="kolecko" @click="zmenBarvu()"></div>
</template>

<style scoped>
    .kolecko {
        height: 7rem;
        width: 7rem;
        border-radius: 50%;
        transition: all 2s ease-in-out;
        cursor: pointer;
        background-color: v-bind(barvaKolecka);
    }
</style>