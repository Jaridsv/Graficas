<!-- ChartComponent.vue -->

<template>
  <div>
    <canvas ref="chartCanvas" width="400" height="200"></canvas>
  </div>
</template>

<script>
import { Chart } from 'chart.js';

import axios from 'axios';

export default {
  data() {
    return {
      chartData: null,
    };
  },
  mounted() {
    this.fetchChartData();
  },
  methods: {
    async fetchChartData() {
      try {
        const response = await axios.get(
          'https://eodhistoricaldata.com/api/eod/AAPL.US',
          {
            params: {
              from: '2017-01-05',
              to: '2017-02-05',
              api_token: 'OeAFFmMliFG5orCUuwAKQ8l4WWFQ67YX', // Reemplaza con tu clave de API
            },
          }
        );

        this.chartData = response.data;
        this.renderChart();
      } catch (error) {
        console.error('Error al obtener datos del API:', error);
      }
    },
    renderChart() {
      // Implementa la lógica para renderizar la gráfica usando Chart.js
      const ctx = this.$refs.chartCanvas.getContext('2d');

      new Chart(ctx, {
        type: 'line',
        data: {
          labels: this.chartData.map(entry => entry.date),
          datasets: [
            {
              label: 'Cierre',
              data: this.chartData.map(entry => entry.close),
              borderColor: 'blue',
              fill: false,
            },
          ],
        },
      });
    },
  },
};
</script>

<style scoped>
/* Añade estilos según tus necesidades */
</style>
