<script setup>
import { ref } from "vue"

const oblibenaBarva = ref("cervena");
const zaskrtnuto = ref();
const poleOvoce = ref([]);
const velikostTricka = ref("");
const poleZelenina = ref([]);
const variantaTasky = ref();
const zprava = ref("");

</script>

<template>
    <h3>Direktiva v-model</h3>

    <div>
        <!-- two way binding -->
        <!-- input:text, input:number, input:color, atd... vraci string -->
        <p>Oblibena barva: {{ oblibenaBarva }}</p>
        <input type="text" v-model="oblibenaBarva">
    </div>

    <hr>

    <div>
        <!-- input:checkbox vraci boolean -->
        <p>Checkbox: {{ zaskrtnuto }}</p>
        <input type="checkbox" v-model="zaskrtnuto">
    </div>

    <hr>

    <div>
        <!-- input:checkbox a v-model dostal pole, tak se value checkboxu do pole vlozi -->
        <p>Vybrane ovoce: {{ poleOvoce }}</p>
        <div>Ananas</div>
        <input type="checkbox" value="ananas" v-model="poleOvoce">
        <div>Kiwi</div>
        <input type="checkbox" value="kiwi" v-model="poleOvoce">
        <div>Pomeranc</div>
        <input type="checkbox" value="pomeranc" v-model="poleOvoce">
        <div>Jablko</div>
        <input type="checkbox" value="jablko" v-model="poleOvoce">
    </div>

    <hr>

    <div>
        <!-- select vraci string -->
        <p>Velikost tricka: {{ velikostTricka }}</p>
        <select v-model="velikostTricka">
            <option disabled value="">Vyberte</option>
            <option value="male">S</option>
            <option value="stredni">M</option>
            <option value="velke">L</option>
        </select>
    </div>

    <hr>

    <div>
        <!-- select:multiple pokud je v-modle promenna pole, tak se vybrane polozky vlozi do pole jako prvky pole -->
        <p>Vybrana zelenina: {{ poleZelenina }}</p>
        <select v-model="poleZelenina" multiple>
            <option value="cibule">Cibule</option>
            <option value="mrkev">Mrkev</option>
            <option value="cuketa">Cuketa</option>
            <option value="brambora">Brambora</option>
        </select>
    </div>

    <hr>

    <div>
        <!-- input:radio vraci string -->
        <!-- pokud radio buttony maji uvnitr v-modelu stejnyou promennou, tak je vue automaticky seskupi (je pak mozne vybrat jen jednu moznost) -->
        <p>Varianta tasky: {{ variantaTasky }}</p>
        <div>Plastova</div>
        <input type="radio" value="plastova" v-model="variantaTasky">
        <div>Latkova</div>
        <input type="radio" value="latkova" v-model="variantaTasky">
        <div>Papirova</div>
        <input type="radio" value="papirova" v-model="variantaTasky">
    </div>

    <hr>

    <div>
        <!-- textarea je parovy tag elemnt -->
        <!-- html automaticky odstranuje entery a mezery navic -->
        <!-- pokud uvnitr lementu chceme zobrazit nove radky, tak je porteba pridat CSS style white-space: pre-line -->
        <p style="white-space: pre-line;">Vase zprava: {{ zprava }}</p>
        <textarea v-model="zprava"></textarea>
    </div>
</template>

<style scoped></style>