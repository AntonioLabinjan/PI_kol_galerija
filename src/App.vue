<template>
  <div>
    <h1>Galerija slika</h1>

    <div style="display: flex; gap: 20px;">
      <Slika
        v-for="(slikaObj, index) in galerija"
        :key="index"
        :slikar="slikaObj.slikar"
        :godina="slikaObj.godina"
        :naslov="slikaObj.naslov"
        :slika="slikaObj.slika"
        @povecaj="azurirajPovecanu"
      />
    </div>

    <div v-if="povecana_slika">
      <h2>Povećana slika:</h2>
      <img :src="povecana_slika" alt="Povećana slika" style="max-height: 400px;" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Slika from './components/Slika.vue'

const galerija = [
  {
    slikar: "Pablo Picasso",
    godina: 1903,
    naslov: "The Old Guitarist",
    slika: "/slike/The Old Guitarist.jpg"
  },
  {
    slikar: "Vincent van Gogh",
    godina: 1886,
    naslov: "Le Moulin de Blute-Fin",
    slika: "/slike/le_moulin.jpg"
  },
  {
    slikar: "Hokusai",
    godina: 1890,
    naslov: "Courtesan Asleep",
    slika: "/slike/courtesan.jpg"
  }
]

const povecana_slika = ref('')

function azurirajPovecanu(slikaSrc) {
  povecana_slika.value = slikaSrc
}
</script>
