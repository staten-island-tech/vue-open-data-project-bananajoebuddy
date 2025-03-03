<template>
    <div>
      <h2>{{ pokemon.name }}</h2>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue'
  import { useRoute } from 'vue-router'
  const route = useRoute()
  const pokemon = ref('')
  
  async function getPokemon() {
    let res = await fetch('https://pokeapi.co/api/v2/pokemon/${route.params.id}')
    let data = await res.json()
    pokemon.value = data
  }
  
  onMounted(() => {})
  </script>
  <!-- use a link use that route and extract data from it, you want the id number, use route-->
  <style scoped></style>
  