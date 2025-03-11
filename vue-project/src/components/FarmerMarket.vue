<template>
  <div>{{ lslsgerf }}</div>
</template>

<script setup>
import { onMounted } from 'vue'

async function skidsfhsa() {
  const res = await fetch('https://data.cityofnewyork.us/resource/8vwk-6iz2.json')
  const data = await res.json()
  console.log(data)
  lslsgerf.push(data)
}

onMounted(() => {
  skidsfhsa()
})

let lslsgerf = ['']
</script>

<style scoped></style>
