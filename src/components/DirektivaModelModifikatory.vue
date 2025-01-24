<script setup>
import {ref, computed} from "vue"

const jmeno = ref("");
const cisloA = ref(0);
const cisloB = ref(0);
const suma = computed(() => {
    return cisloA.value + cisloB.value;
});
const email = ref("");

</script>


<template>
    <h3>Direktiva v-model (modifikatory)</h3>
    <!-- lazy promenna se zmeni az po blur inputu-->    
    <label for="">
        Zadejte jmeno:
        <input v-model.lazy="jmeno" type="text">
    </label>
    <p>Vase jmeno: {{ jmeno }}</p>
    
    <!-- number prevede string na number-->
    <hr>
    <label for="">
        Zadejte dve cisla:
        <input v-model.number="cisloA" type="text">
        <input v-model="cisloB" type="number">
    </label>
    <p>Suma dvou cisel: {{ suma }}</p>

    <!-- trim odstrani vsechny mezery pred a za textem-->
    <hr>
    <label for="">
        Zadejte email:
        <input v-model.trim="email" type="text">
    </label>
    <p style="white-space: pre;">Vas email: [{{ email }}]</p>
    
</template>

<style scoped>
</style>