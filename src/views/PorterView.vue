<template>
  <div>
    <select v-model="selectedOption" style="width: 50%; margin-left: 50%; height: 30px; border-radius: 0.5rem;">
      <option value="ปิยวัฒน์ แสนนาง">ปิยวัฒน์ แสนนาง</option>
      <option value="อุทุมพร แสงเมือง">อุทุมพร แสงเมือง</option>
      <option value="หฤษฎ์ จิ๋วแก้ว">หฤษฎ์ จิ๋วแก้ว</option>
      <option value="พงษ์พันธ์ ดีเลิศ">พงษ์พันธ์ ดีเลิศ</option>
    </select>
    <p style="margin-left: 90%;">{{ selectedOption }}</p>
  </div>
  <div class="date">
    <input type="date">
  </div>
  <br>
  <div class="grid">
    <div class="box">รับแล้ว<br><br>6</div>
    <div class="box">งานที่ปฏิเสธ<br><br>0</div>
    <div class="box">งานที่สำเร็จ<br><br>5</div>
    <div class="box">เวลาเฉลี่ย<br><br>5:07</div>
  </div>
  <br>
  <table>
    <thead>
      <tr>
        <th>เวลา</th>
        <th>จาก</th>
        <th>ถึง</th>
        <th>สถานะ</th>
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
      selectedOption: '',
      tasks: [
        { time: '-', from: 'ห้องฉุกเฉิน', to: 'ห้องพัก1', status: '🟡กำลังดำเนินการ' },
        { time: '15:30', from: 'ห้องฉุกเฉิน', to: 'ห้องพัก2', status: '🟢เสร็จสิ้น' },
        { time: '14:07', from: 'ห้องฉุกเฉิน', to: 'ห้องพัก3', status: '🟢เสร็จสิ้น' },
        { time: '13:07', from: 'ห้องฉุกเฉิน', to: 'ห้องพัก4', status: '🟢เสร็จสิ้น' },
        { time: '12:07', from: 'ห้องฉุกเฉิน', to: 'ห้องพัก5', status: '🟢เสร็จสิ้น' },
        { time: '11:07', from: 'ห้องฉุกเฉิน', to: 'ห้องพัก6', status: '🟢เสร็จสิ้น' }
      ]
    }
  }
}
</script>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
  background: #FFFFFF;
}
th,td {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
  text-align: center;
}
.card1 {
  border: 1px solid #dddddd;
  text-align: center;
  padding: 8px; 
  width: auto;
}
.card2 {
  border: 1px solid #dddddd;
  text-align: center;
  padding: 8px; 
  width: auto;
}
.card3 {
  border: 1px solid #dddddd;
  text-align: center;
  padding: 8px; 
  width: auto;
}
.card4 {
  border: 1px solid #dddddd;
  text-align: center;
  padding: 8px; 
  width: auto;
}
.content-body{
  background: #FFFFFF;
  width: 50%;
}
.row{
  display: flex;
}
.col-md-4{
  width: 200px;
  border: 1px solid #dddddd;
  text-align: center;
  padding: 8px;
}
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 1rem;
}

.box {
  background-color: #ffffff;
  padding: 1rem;
  border-radius: 0.5rem;
  width: auto;
  height: auto;
  text-align: center;
  font-size: 20px;
}
</style>