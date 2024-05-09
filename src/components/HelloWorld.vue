<template>
  <div class="date">
    <input type="date">
  </div><br>
  <div class="column1">
    <div class="linechart">
      <canvas ref="myChart"></canvas>
    </div>
    <div class="barchart">
      <canvas ref="deliveryChart"></canvas>
    </div>
  </div>
  <br>
  <div class="leaderboard">
    <h2>อันดับการทำงาน</h2>
    <table>
      <thead>
        <tr>
          <th>รูป</th>
          <th>ชื่อ</th>
          <th>รอบการส่ง</th>
          <th>เวลาเฉลี่ย</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(player, index) in players" :key="index">
          <td>
            <img :src="player.avatar" alt="Player Avatar" class="avatar">
          </td>
          <td>{{ player.name }}</td>
          <td>{{ player.round }}</td>
          <td>{{ player.time }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import { Chart, registerables } from 'chart.js';

export default defineComponent({
  mounted() {
    const lineCtx = this.$refs.myChart.getContext('2d');
    const deliveryCtx = this.$refs.deliveryChart.getContext('2d');
    Chart.register(...registerables);

    // Line chart
    new Chart(lineCtx, {
      type: 'line',
      data: {
        labels: ['มกราคม', 'กุมภาพันธ์', 'มีนาคม', 'เมษายน', 'พฤษภาคม', 'มิถุนายน', 'กรกฎาคม', 'สิงหาคม', 'กันยายน', 'ตุลาคม', 'พฤศจิกายน', 'ธันวาคม'],
        datasets: [{
          label: 'การส่งรวมของแต่ละเดือน',
          data: [65, 59, 80, 81, 56, 55, 40, 45, 55, 60, 70, 75],
          borderWidth: 1
        }]
      },
      options: {
        scales: {
          y: {
            beginAtZero: true
          }
        },
        responsive: true,
        maintainAspectRatio: false
      }
    });

    // Bar chart
    new Chart(deliveryCtx, {
      type: 'bar',
      data: {
        labels: ['จันทร์', 'อังคาร', 'พุธ', 'พฤหัสบดี', 'ศุกร์', 'เสาร์', 'อาทิตย์'],
        datasets: [{
          label: 'การส่งของแต่ละอาทิตย์',
          data: [12, 19, 3, 5, 2, 3, 7],
          backgroundColor: [
            'rgba(255, 99, 132, 0.2)',
            'rgba(54, 162, 235, 0.2)',
            'rgba(255, 206, 86, 0.2)',
            'rgba(75, 192, 192, 0.2)',
            'rgba(153, 102, 255, 0.2)',
            'rgba(255, 159, 64, 0.2)',
            'rgba(255, 99, 132, 0.2)'
          ],
          borderColor: [
            'rgba(255, 99, 132, 1)',
            'rgba(54, 162, 235, 1)',
            'rgba(255, 206, 86, 1)',
            'rgba(75, 192, 192, 1)',
            'rgba(153, 102, 255, 1)',
            'rgba(255, 159, 64, 1)',
            'rgba(255, 99, 132, 1)'
          ],
          borderWidth: 1
        }]
      },
      options: {
        scales: {
          y: {
            beginAtZero: true
          }
        },
        responsive: true,
        maintainAspectRatio: false
      }
    });
  },
  data() {
    return {
      players: [
        { name: 'ปิยวัฒน์ แสนนาง', round: 3, time: '01:24', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'หฤษฎ์ จิ๋วแก้ว', round: 2, time: '01:31', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'อุทุมพร แสงเมือง', round: 2, time: '01:17', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'พงษ์พันธ์ ดีเลิศ', round: 1, time: '01:39', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' }
      ]
    }
  }

});  
</script>

<style scoped>
.linechart{
  width: 450px;
  height: 300px!important;
  background: #FFFFFF;
  border-radius: 0.5rem;
}
.barchart{
  width: 450px;
  height: 300px!important;
  background: #FFFFFF;
  border-radius: 0.5rem;
}
.leaderboard {
  background-color: #ffffff;
  color: #000000;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  width: 70%;
}
.column1{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr; 
  gap: 10px;
}
h2 {
  margin-bottom: 20px;
}
table {
  width: 100%;
  border-collapse: collapse;
}
th, td {
  padding: 10px;
  text-align: left;
}
th {
  background-color: #DCDCDC;
  font-weight: bold;
}
td {
  border-bottom: 1px solid #D3D3D3;
}
.avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}
</style>
