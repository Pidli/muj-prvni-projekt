<script setup>
import {computed, ref} from "vue"

const cilOdkazu = ref('');
function zmenCilOdkazu(argNovyCil) {
    cilOdkazu.value = argNovyCil;
}

const typInputu = ref('checkbox');
function zmenTypInputu(argNovyTyp) {
    typInputu.value = argNovyTyp;
}

const zakazano = ref(true);
function zmenStavZakazano() {
    zakazano.value = !zakazano.value;
}
const textTlacitka = computed(() => {
    if (zakazano.value == true) {
        return "Povolit input";
    }else{
        return "Zakazat input";
    }
});

</script>

<template>
    <h3>Direktiva v-bind (zaklady)</h3>
    <button v-on:click="zmenCilOdkazu('https://primakurzy.cz')">primakurzy</button>
    <button v-on:click="zmenCilOdkazu('https://google.com')">google</button>
    <button v-on:click="zmenCilOdkazu('https://seznam.cz')">seznam</button>

    <p>
        <a v-bind:href="cilOdkazu" target="_blank">Otevri nove okno</a>   
    </p>
    
    <hr>

    <button @click="zmenTypInputu('radio')">radio</button>
    <button @click="zmenTypInputu('checkbox')">checkbox</button>

    <form action="" method="post">
        <input :type="typInputu" name="" id="">
    </form>

    <hr>

    <button @click="zmenStavZakazano()">{{ textTlacitka }}</button>
    <input type="text" name="" id="" :disabled="zakazano">
</template>


<style scoped>

</style>