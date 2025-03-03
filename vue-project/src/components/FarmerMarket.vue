<template>
    <router-link :to="pkmnPath">
      <h2>{{ mon.name }}</h2>
      <h3>{{ index + 1 }}</h3>
    </router-link>
  </template>
  
  <script setup>
  import { computed } from 'vue'
  const props = defineProps({
    pokemon: Object,
    id: Number,
  })
  
  constpkmnPath = computed(() => {
    return '/pokemon/$props.id'
  })
  
  defineProps({
    name: String,
    index: Number,
  })
  </script>
  
  <style scoped>
  .card {
    width: 20%;
    height: 20%;
    background-color: blanchedalmond;
  }
  </style>
  