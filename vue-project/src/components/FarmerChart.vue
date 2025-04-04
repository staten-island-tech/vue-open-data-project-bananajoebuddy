<template>
    <div>
      <canvas ref="chartCanvas"></canvas>
      <canvas ref="ebtChartCanvas"></canvas>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, watch } from 'vue';
  import { Chart } from 'chart.js';
  
  const props = defineProps({
    marketData: Array,
  });
  
  const chartCanvas = ref(null);
  const ebtChartCanvas = ref(null);
  
  const createBarChart = () => {
    const ctx = chartCanvas.value.getContext('2d');
  
    const boroughs = props.marketData.reduce((acc, market) => {
      const borough = market.borough || 'Unknown';
      acc[borough] = (acc[borough] || 0) + 1;
      return acc;
    }, {});
  
    const labels = Object.keys(boroughs);
    const data = Object.values(boroughs);
  
    new Chart(ctx, {
      type: 'bar',
      data: {
        labels: labels,
        datasets: [{
          label: 'Number of Markets',
          data: data,
          backgroundColor: '#42A5F5',
        }],
      },
      options: {
        responsive: true,
        scales: {
          y: {
            beginAtZero: true,
          },
        },
      },
    });
  };
  
  const createEbtChart = () => {
    const ctx = ebtChartCanvas.value.getContext('2d');
  
    const ebtCount = props.marketData.reduce((acc, market) => {
      const acceptsEbt = market.accepts_ebt === 'YES';
      acc[acceptsEbt ? 'accepts' : 'doesNotAccept'] += 1;
      return acc;
    }, { accepts: 0, doesNotAccept: 0 });
  
    new Chart(ctx, {
      type: 'pie',
      data: {
        labels: ['Accepts EBT', 'Does Not Accept EBT'],
        datasets: [{
          data: [ebtCount.accepts, ebtCount.d
  