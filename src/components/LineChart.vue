<template>
    <div>
      <canvas ref="myChart"></canvas>
    </div>
</template>
  
  <script>
  import { defineComponent } from 'vue';
  import { Chart, registerables } from 'chart.js';
  
  export default defineComponent({
    mounted() {
      const ctx = this.$refs.myChart.getContext('2d');
      Chart.register(...registerables);
      
      new Chart(ctx, {
        type: 'line',
        data: {
          labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
          datasets: [{
            label: 'Work Graph',
            data: [65, 59, 80, 81, 56, 55, 40, 45, 55, 60, 70, 75],
            borderWidth: 1
          }]
        },
        options: {
          scales: {
            y: {
              beginAtZero: true
            }
          }
        }
      });
    }
  });
  </script>
  
<style scoped>
 
</style>
  