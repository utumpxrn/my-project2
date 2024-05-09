<template>
  <div>
    <canvas ref="deliveryChart"></canvas>
  </div>
</template>

<script>
import Chart from 'chart.js/auto';
import ChartDataLabels from 'chartjs-plugin-datalabels';
Chart.register(ChartDataLabels);

export default {
  name: 'DeliveryChart',
  data() {
    return {
      deliveryChart: null,
    };
  },
  mounted() {
    this.createChart();
  },
  methods: {
    createChart() {
      const data = {
        labels: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'],
        datasets: [
          {
            label: 'Delivery Today',
            data: [7, 15, 8, 12, 6, 19, 23],
            backgroundColor: ['fuchsia', 'lightblue', 'navy', 'yellow', 'fuchsia', 'gold', 'pink'],
          },
        ],
      };

      const config = {
        type: 'bar',
        data: data,
        options: {
          plugins: {
            datalabels: {
              display: true,
              color: 'white',
              anchor: 'end',
              align: 'top',
              offset: 2,
              font: {
                weight: 'bold'
              }
            }
          },
          scales: {
            x: {
              display: false,
            },
            y: {
              beginAtZero: true,
            },
          },
        },
      };

      const ctx = this.$refs.deliveryChart.getContext('2d');
      this.deliveryChart = new Chart(ctx, config);
      Chart.register(...registerables);
    },
  },
};
</script>