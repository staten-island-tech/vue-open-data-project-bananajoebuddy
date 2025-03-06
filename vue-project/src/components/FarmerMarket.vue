<template>
  <div>

  </div>
</template>

<script setup>

async function skidsfhsa() {
    let res = await fetch('https://data.cityofnewyork.us/api/odata/v4/8vwk-6iz2')
    let data = await res.json()
    lklkgerf.value = data
  }

</script>

<style scoped>

</style>