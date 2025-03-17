<template>
  <div>{{ lslsgerf }}</div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const lslsgerf = ref([''])
async function skidsfhsa() {
  const res = await fetch('https://data.cityofnewyork.us/resource/8vwk-6iz2.json')
  const data = await res.json()
  lslsgerf.value = data
  console.log(data)
}
onMounted(() => {
  skidsfhsa()
})
</script>

<style scoped></style>
