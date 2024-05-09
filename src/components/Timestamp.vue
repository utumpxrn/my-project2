<script setup>


</script>
<template>
  <!-- <header>
    <MyBar/>
  </header> -->

    <table>
      <thead>
        <tr>
          <th>Picture</th>
          <th>Name</th>
          <th>Round</th>
          <th>Times</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(person, index) in people" :key="index">
          <td><img :src="person.image" style="width:50px;height:50px;" alt="person"></td>
          <td>{{ person.name }}</td>
          <td>{{ person.round }}</td>
          <td>{{ person.time }}</td>
        </tr>
      </tbody>
    </table>
  </template>
  
  <script>
  export default {
    data() {
      return {
        people: [
          { image: 'path/to/image1.jpg', name: 'Piyawat Saennang', round: 1, time: '10:00' },
          { image: 'path/to/image2.jpg', name: 'Utumporn Saengmueang', round: 2, time: '11:00' },
          { image: 'path/to/image3.jpg', name: 'Harit Jewkaew', round: 3, time: '12:00' },
          { image: 'path/to/image3.jpg', name: 'Pongpan Beeblert', round: 3, time: '12:00' }

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
  }
  th {
    background-color: #f2f2f2;
  }
  </style>