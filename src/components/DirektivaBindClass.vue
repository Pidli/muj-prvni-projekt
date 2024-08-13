<script setup>
import {ref, computed} from "vue"

//toto je prace s dynamickou class pomoci stringu 
//tento zpusob je jednoduchy, ale hodi se jen pro pripady, kdy chceme naraz vlosit celous sadu trid nebo naraz odstranit celou sadu
const classString = ref('');
setTimeout(() => {
    classString.value = "zvyrazneno velky"
}, 5000);

//pokud chceme flexibilnejsi zpusob, tak pouzijeme objekt nebo array
const objektTrid = ref({
    velky: false,
    zvyrazneno: false
});
function zmenClassuVelky() {
    objektTrid.value.velky = !objektTrid.value.velky;
}
function zmenClassuZvyrazneno() {
    objektTrid.value.zvyrazneno = !objektTrid.value.zvyrazneno;
}

//nyni si ukazeme jak vygenerovat computed objekt pomoci reaktivnich promennych
const pocitadlo = ref(0);
const jeObarveno = ref(false);
const computedObjektTrid = computed(() => {
    const objekt = {
        obarveno: jeObarveno.value,
        podtrzeno: jeObarveno.value && pocitadlo.value > 5
    };
    return objekt;
});
function zmenStavObarveno() {
    jeObarveno.value = !jeObarveno.value;
}

//nyni se podivame na pridavani a odebirani class pomoci pole
const class1 = ref('zvyrazneno');
const class2 = ref('velky');
const computedPoleTrid = computed(() => {
    const pole = [
        class1.value,
        class2.value
    ];
    return pole;
});
setTimeout(() => {
    class2.value = "";
}, 5000);

</script>

<template>
    <h3>Direktiva v-bind (class)</h3>
    <h4>Dynamicka class pomoci stringu</h4>
    <div class="kolecko" :class="classString"></div>

    <hr>
    <h4>Dynamicka class pomoci objektu</h4>
    <button @click="zmenClassuVelky()">Class velky</button>
    <button @click="zmenClassuZvyrazneno()">Class zvyrazneno</button>
    <div class="kolecko" :class="objektTrid"></div>

    <hr>
    <h4>Dynamicka class pomoci computed objektu</h4>
    <button @click="pocitadlo++">Zvedni pocitadlo</button>
    <button @click="zmenStavObarveno()">Obarvi/Odbarvi paragraf</button>
    <p :class="computedObjektTrid">Tento paragraf se podtrhne pokud bude obarveny a zaroven bude pocitadlo vyssi nez 5. Aktualni stav pocitadla: {{ pocitadlo }}</p>
    
    <hr>
    <h4>Dynamicka class pomoci pole</h4>
    <div class="kolecko" :class="computedPoleTrid"></div>
</template>

<style scoped>
    .kolecko {
        height: 7rem;
        width: 7rem;
        background-color: black;
        border-radius: 50%;
        transition: 1s all ease-in-out;
    }

    .kolecko.velky {
        height: 10rem;
        width: 10rem;
    }

    .kolecko.zvyrazneno {
        background-color: crimson;
    }

    .obarveno {
        color: yellowgreen;
    }

    .podtrzeno {
        text-decoration: underline;
    }
</style>