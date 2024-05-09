<template>
  <div class="dashboard-content">
      <div class="content-header">
        <div class="col-md-4">
            <div class="card">
              <div class="card-body">
                <h5 class="content-body">Utumporn Saengmueang <button class="btn">
                <i class="mdi mdi-menu-down" style="margin-left: 120px;"></i></button></h5>
              </div>
            </div>
          </div>
        </div>
        <div class="date">
      <input type="date">
    </div>
    <br>
      <div class="content-body">
        <div class="row">
          <div class="col-md-4">
            <div class="card">
              <div class="card-body">
                <h1 class="card-title">Finish task</h1>
                <p class="card-text">12</p>
              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="card">
              <div class="card-body">
                <h5 class="card-title">Averagetime</h5>
                <p class="card-text">45.67</p>
              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="card">
              <div class="card-body">
                <h5 class="card-title">Rejected task</h5>
                <p class="card-text">1</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <table>
      <thead>
        <tr>
          <th>Time</th>
          <th>From</th>
          <th>To</th>
          <th>Status</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="task in tasks" :key="task.id">
            <td>{{ task.time }}</td>
            <td>{{ task.from }}</td>
            <td>{{ task.to }}</td>
            <td>{{ task.status }}</td>
          </tr>
      </tbody>
    </table>
</template>
<script>
  export default {
  data() {
    return {
      name: 'Piyawat Saennang',
      currentDate: '05/MM/YYYY',
      finishedTasks: 12,
      rejectedTasks: 1,
      averageTime: 15.51,
      tasks: [
        { time: '16.40, 16:48', from: 'Hostel of veterinarian', to: 'medicine room', status: '🟢Complete' },
        { time: '15.30, 15:42', from: 'medical veterinarian', to: 'medicine room', status: '🟢Complete' },
        { time: '14.07, 14:12', from: 'medical veterinarian', to: 'medicine room', status: '🟢Complete' },
        { time: '13.05, 13:21', from: 'medical veterinarian', to: 'medicine room', status: '🟢Complete' },
        { time: '10.11, 10:16', from: 'medical veterinarian', to: 'medicine room', status: '🟢Complete' },
        { time: '10:00, 10:11', from: 'medical veterinarian', to: 'medicine room', status: '🟢Complete' },
        { time: '09:42, 09:54', from: 'medical veterinarian', to: 'medicine room', status: '🟢Complete' },
        { time: '09:25, 09:31', from: 'medical veterinarian', to: 'medicine room', status: '🟢Complete' },
      ]
    }
  }
}
</script>
  
<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
}
th, td {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}
th {
  background-color: #f2f2f2;
}
</style>