<template>
  <div class="about">
    <FarmerChart />
  </div>
</template>

<script setup>
import FarmerChart from '../components/FarmerChart.vue'
</script>

<style scoped>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

