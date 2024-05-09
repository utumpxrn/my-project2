<template>
  <div class="leaderboard">
    <h2>Leaderboard</h2>
    <table>
      <thead>
        <tr>
          <th>Picture</th>
          <th>Name</th>
          <th>Round</th>
          <th>Time</th>
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
export default {
  data() {
    return {
      players: [
        { name: 'Player 1', round: 3, time: '01:24', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'Player 2', round: 2, time: '01:31', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'Player 3', round: 4, time: '01:17', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'Player 4', round: 1, time: '01:39', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'Player 5', round: 3, time: '01:26', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'Player 6', round: 2, time: '01:33', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'Player 7', round: 4, time: '01:20', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' },
        { name: 'Player 8', round: 1, time: '01:41', avatar: 'https://th.bing.com/th/id/OIP.audMX4ZGbvT2_GJTx2c4GgHaHw?rs=1&pid=ImgDetMain' }
      ]
    }
  }
}
</script>

<style scoped>
.leaderboard {
  background-color: #131b25;
  color: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  width: 70%;
  
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
  background-color: #1F2C42;
  font-weight: bold;
}
td {
  border-bottom: 1px solid #1F2C42;
}
.avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}
</style>