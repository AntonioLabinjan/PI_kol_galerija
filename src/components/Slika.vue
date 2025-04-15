<!-- src/components/Slika.vue -->
<template>
    <div>
      <img 
        :src="slika" 
        @click="$emit('povecaj', slika)" 
        :alt="naslov" 
        height="100"
      />
      <p :class="{ underline: starost() > 136 }"><strong>{{ naslov }}</strong></p>
      <p>{{ slikar }}</p>
      <p>Starost: {{ starost() }} godina</p>
    </div>
  </template>
  
  <script setup>
  const props = defineProps(['slikar', 'godina', 'naslov', 'slika'])

function starost() {
  const trenutnaGodina = new Date().getFullYear()
  return trenutnaGodina - props.godina
}
  </script>
  
  <style scoped>
  .underline {
    text-decoration: underline;
  }
  </style>
  