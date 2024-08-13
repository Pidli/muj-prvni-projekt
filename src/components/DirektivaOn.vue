<script setup>
import {ref} from "vue";
//pocitadlo
const pocitadlo = ref(0);
function odeber() {
    pocitadlo.value--;
}


//objekt event, odposlouchavni klavesnice
const znak = ref("nic");
const kod = ref("nic");
function zjistiKlavesu(argObjektEvent) {
    //objekt event/udalost/e
    znak.value = argObjektEvent.key;
    kod.value = argObjektEvent.code;
}


//ukazka preventDefault
function pozdrav(argText) {
    //argObjektEvent.preventDefault();
    alert(argText);
}
</script>

<template>
    <h3>Direktiva v-on</h3>
    <!-- direktiva v-on se stara o udalosti -->
    <p>Pocitadlo: {{ pocitadlo }}</p>
    <button v-on:click="pocitadlo++">Pridat</button>
    <button v-on:click="odeber()">Odebrat</button>
    <!-- zkraceny zapis pro direktivu v-on -->
    <button @click="pocitadlo=0">Reset</button>

    <!-- horizontal rule -->
    <hr>

    <input @keyup="zjistiKlavesu($event)" type="text" name="" id="">
    <p>Znak klavesy: {{ znak }}</p>
    <p>Kod klavesy: {{ kod }}</p>

    <hr>

    <p>
        <a v-on:click.prevent="pozdrav('Cau!')" href="">Pozdrav Cau!</a>
    </p>
    <p>
        <a @click.prevent="pozdrav('Ahoj!')" href="">Pozdrav Ahoj!</a>
    </p>
</template>

<style scoped>
hr {
    margin: 0.5rem 0rem;
}
</style>