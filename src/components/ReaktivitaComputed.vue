<script setup>
//1) problem
//2) reseni pomoci funkce
//3) reseni pomoci computed
//4) good practices (nahradit ternarni operatory za computed, read-only, nikdy nemenit stav reaktivnich pormennych uvnitr funkce computed)
import {ref, computed} from "vue"

const poleCisel = ref([11, 74, 52, 81, 64]);

//toto je funkce ktera zjisti aktulani sumu pole
function zjistiSumu() {
    let sumaPole = 0;
    for (let cislo of poleCisel.value) {
        sumaPole += cislo;
    }
    return sumaPole; 
}

//zde vytvorime novou reaktivni pormenou typu computed
//computed prijima v parametru arrow funkci
//narozdil od promenne typu ref, tak promenna typu computed je read-only
//na rozdil of funkce tak template blok honodtu prekresli jen pokud se zmenily hodnoty zavislosti (setri vykon pocitace)
const sumaComputed = computed(() => {
    let sumaPole = 0;
    for (let cislo of poleCisel.value) {
        sumaPole += cislo;
    }
    return sumaPole;     
});

const sudostComputed = computed(() => {
    if (sumaComputed.value % 2 == 0) {
        return "Ano";
    }else{
        return "Ne";
    }
});

//toto vlozi do pole nove cislo po tom co ubehne 5 sekund
setTimeout(() => {
    poleCisel.value.push(Math.floor(Math.random() * 100));
}, 5000);

</script>

<template>
    <h3>Reaktivita computed</h3>
    <p>Pole cisel: {{ poleCisel }}</p>
    <p>Suma pole (funkce): {{ zjistiSumu() }}</p>
    <p>Suma pole (computed): {{ sumaComputed }}</p>
    <p>Je suma suda? {{ sumaComputed%2 ? "Ne" : "Ano" }}</p>
    <p>Je suma suda? {{ sudostComputed }}</p>
</template>