<template>
  <div v-for="(item, index) in lslsgerf" :key="index" class="card">
    <h2>{{ item.marketname }}</h2>
    <p><span class="IMPORTANT">Borough: </span>{{ item.borough }}</p>
    <p><span class="IMPORTANT">Address: </span>{{ item.streetaddress }}</p>
    <p><span class="IMPORTANT">Community district: </span>{{ item.community_district }}</p>
    <p><span class="IMPORTANT">Days operation: </span>{{ item.daysoperation }}</p>
    <p><span class="IMPORTANT">Hours opeation:</span>{{ item.hoursoperations }}</p>
    <p><span class="IMPORTANT">Accepts EBT?:</span>{{ item.accepts_ebt }}</p>
    <p><span class="IMPORTANT">Open year round?:</span>{{ item.open_year_round }}</p>
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

.IMPORTANT {
  font-weight: bold;
}
</style>
