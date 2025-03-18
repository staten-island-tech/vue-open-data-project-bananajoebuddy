<template>
  <div v-for="(item, index) in lslsgerf" :key="index" class="card">
    <h2>{{ item.marketname }}</h2>
    <p>Borough: {{ item.borough }}</p>
    <p>Address: {{ item.streetaddress }}</p>
    <p>Community district: {{ item.community_district }}</p>
    <p>Days operation:{{ item.daysoperation }}</p>
    <p>Hours opeation:{{ item.hoursoperations }}</p>
    <p>Accepts EBT?:{{ item.accepts_ebt }}</p>
    <p>Open year round?:{{ item.open_year_round }}</p>
  </div>
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

<style scoped>
.card {
  width: 20%;
  height: max-content;
  background-color: skyblue;
}
</style>
