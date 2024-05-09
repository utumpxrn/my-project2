<template>
  <h2 style="text-align: center;">บันทึกเวลาการทำงาน</h2>
  <div class="date" style="margin-left: 90%;">
    <input type="date">
  </div>
  <br>
    <table>
      <thead>
        <tr>
          <th>ชื่อ</th>
          <th>เริ่มงาน</th>
          <th>จบงาน</th>
          <th>วันที่</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(person, index) in people" :key="index">
          <td>{{ person.name }}</td>
          <td>{{ person.start }}</td>
          <td>{{ person.end }}</td>
          <td>{{ person.date }}</td>
        </tr>
      </tbody>
    </table>
  </template>
  
  <script>
  export default {
    data() {
      return {
        people: [
          { name: 'ปิยวัฒน์ แสนนาง', start: '10:03', end: '10:15', date: '20/4/67' },
          { name: 'อุทุมพร แสงเมือง', start: '10:12', end: '10:24', date: '20/4/67' },
          { name: 'หฤษฎ์ จิ๋วแก้ว', start: '10:36', end: '10:44', date: '20/4/67' },
          { name: 'พงษ์พันธ์ ดีเลิศ', start: '12:36', end: '12:47', date: '20/4/67' },
          { name: 'อุทุมพร แสงเมือง', start: '11:36', end: '11:47', date: '20/4/67' },
          { name: 'ปิยวัฒน์ แสนนาง', start: '10:36', end: '10:47', date: '20/4/67' },
          { name: 'หฤษฎ์ จิ๋วแก้ว', start: '09:36', end: '09:47', date: '20/4/67' },
          { name: 'พงษ์พันธ์ ดีเลิศ', start: '08:36', end: '08:47', date: '20/4/67' },
          { name: 'พงษ์พันธ์ ดีเลิศ', start: '07:36', end: '07:47', date: '20/4/67' }
        ]
      };
    }
  };
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
    background-color: #FFFFFF;
    text-align: center;
  }
  th {
    background-color: #f2f2f2;
    text-align: center;
  }
  h2{
    font-size: 32px;
    color: #FFFFFF;
  }
  </style>