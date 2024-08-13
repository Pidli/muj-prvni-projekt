<script setup>
//toto je blok pro js
import NovaKomponenta from "./components/NovaKomponenta.vue"
import ReaktivitaRef from "./components/ReaktivitaRef.vue"
import TextInterpolace from "./components/TextInterpolace.vue"
import ReaktivitaComputed from "./components/ReaktivitaComputed.vue"
import DirektivaOn from "./components/DirektivaOn.vue"
import DirektivaBind from "./components/DirektivaBind.vue"
import CestyObrazku from "./components/CestyObrazku.vue"
import DirektivaBindClass from "./components/DirektivaBindClass.vue"
import DirektivaBindStyleCSS from "./components/DirektivaBindStyleCSS.vue"
import DirektivaShowIf from "./components/DirektivaShowIf.vue"
import DirektivaFor from "./components/DirektivaFor.vue"
import DirektivaBindKey from "./components/DirektivaBindKey.vue"
import DetekceZmenyPole from "./components/DetekceZmenyPole.vue"
import DirektivaModel from "./components/DirektivaModel.vue"
import DirektivaBindValue from "./components/DirektivaBindValue.vue"
</script>

<template>
  <!-- toto je html blok -->
  <div class="container">
    <h1>Kurz Vue</h1>

    <h2>Témata kurzu</h2>

    <div class="karta">
      <NovaKomponenta />
    </div>
    <div class="karta">
      <NovaKomponenta />
    </div>
    <div class="karta">
      <ReaktivitaRef />
    </div>
    <div class="karta">
      <TextInterpolace />
    </div>
    <div class="karta">
      <ReaktivitaComputed />
    </div>
    <div class="karta">
      <DirektivaOn />
    </div>
    <div class="karta">
      <DirektivaBind />
    </div>
    <div class="karta">
      <CestyObrazku />
    </div>
    <div class="karta">
      <DirektivaBindClass />
    </div>
    <div class="karta">
      <DirektivaBindStyleCSS />
    </div>
    <div class="karta">
      <DirektivaShowIf />
    </div>
    <div class="karta">
      <DirektivaFor />
    </div>
    <div class="karta">
      <DirektivaBindKey />
    </div>
    <div class="karta">
      <DetekceZmenyPole />
    </div>
    <div class="karta">
      <DirektivaModel />
    </div>
    <div class="karta">
      <DirektivaBindValue />
    </div>
  </div>
</template>

<style scoped>
/* toto je css blok */
h1 {
  text-align: center;
}

.karta {
  background-color: var(--barva-pozadi-sekundarni);
  border-radius: 0.3rem;
  padding: 1rem;
  margin: 0.8rem;
}
</style>
