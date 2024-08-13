<script setup>
import { ref, computed } from "vue"

//funkce ktere mutuji original
//push, pop, shift, unshift, splice, sort, reverse

//funkce ktere nemutuji original a vraci novou hodnotu
//filter, reduce, concat, slice, ...

//funkce map je na hrane, pokud pole obsahuje jen primitivni datove typy, tak originalni pole zustane stejne, pokud uvnitr funkce map editujeme objekty, tak se obejkty originalniho pole zmeni

const poleCiselOriginal = ref([80, -30, 21, 42, 15, 81, 99, 5, 7]);
//nejprve si ukazeme funkce, ktere original nemutuji

const poleCiselSuda = computed(() => {
    const novePole = poleCiselOriginal.value.filter((cislo) => {
        if (cislo%2 == 0) {
            return true;
        }else{
            return false;
        }
    });
    return novePole;
});

/*
//pokud si nechce zachovat original, tak funkce pouzivejte stejne jako nemutujici funkce
const poleCiselSerazeno = computed(() => {
    poleCiselOriginal.value.sort((cisloA, cisloB) => {
        return cisloA - cisloB;
    });
    return poleCiselOriginal.value;
});
*/

//chceme zachovat original, tak musime zavolat funkci na kopii pole
const poleCiselSerazeno = computed(() => {
    //spread operator ...
    //kopii pole vytvorime pomoci spread operatoru
    const kopiePole = [...poleCiselOriginal.value];
    kopiePole.sort((cisloA, cisloB) => {
        return cisloA - cisloB;
    });
    return kopiePole;
});

</script>

<template>
    <h3>Detekce zmeny pole</h3>

    <h4>original</h4>
    <ul>
        <li v-for="cislo of poleCiselOriginal">{{ cislo }}</li>
    </ul>

    <hr>

    <h4>suda</h4>
    <ul>
        <li v-for="cislo of poleCiselSuda">{{ cislo }}</li>
    </ul>

    <hr>

    <h4>serazeno</h4>
    <ul>
        <li v-for="cislo of poleCiselSerazeno">{{ cislo }}</li>
    </ul>

</template>

<style scoped>
</style>