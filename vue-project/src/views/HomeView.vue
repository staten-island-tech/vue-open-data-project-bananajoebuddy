<template>
  <div class="skibidi">
    <FarmerMarket />
  </div>
</template>

<script setup>
import FarmerMarket from '../components/FarmerMarket.vue'
</script>

<style scoped>
.skibidi {
  display: flex;
  justify-content: space-evenly;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
