<template>
  <div>
    <h2 style="text-align: center;" >รายชื่อพนักงาน</h2>
    <button @click="showModal = true" style="margin-left: 90%;">เพิ่มบุคคล +</button>
    <table>
      <thead>
        <tr>
          <th>ไอดี พนักงาน</th>
          <th>ชื่อ</th>
          <th>ตำแหน่ง</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="employee in employees" :key="employee.id">
          <td>{{ employee.id }}</td>
          <td>{{ employee.name }}</td>
          <td>{{ employee.position }}</td>
        </tr>
      </tbody>
    </table>

    <!-- Modal for adding new employee -->
    <div v-if="showModal" class="modal">
      <div class="modal-content">
        <span class="close" @click="showModal = false">&times;</span>
        <h3>เพิ่มบุคคล</h3>
        <form @submit.prevent="addEmployee">
          <label>
            ไอดี พนักงาน:
            <input v-model="newEmployee.id" required>
          </label>
          <label>
            ชื่อ:
            <input v-model="newEmployee.name" required>
          </label>
          <label>
            ตำแหน่ง:
            <input v-model="newEmployee.position" required>
          </label>
          <button type="submit">เพิ่มบุคคล +</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      employees: [
        { id: '001', name: 'ปิยวัฒน์ แสนนาง', position: 'พนักงานเข็นเปล' },
        { id: '002', name: 'หฤษฎ์ จิ๋วแก้ว', position: 'พนักงานเข็นเปล' },
        { id: '003', name: 'อุทุมพร แสงเมือง', position: 'พนักงานเข็นเปล' },
        { id: '004', name: 'พงษ์พันธ์ ดีเลิศ', position: 'พนักงานเข็นเปล' },
      ],
      showModal: false,
      newEmployee: {
        id: '',
        name: '',
        position: '',
      },
    };
  },
  methods: {
    addEmployee() {
      this.employees.push({ ...this.newEmployee });
      this.newEmployee = {
        id: '',
        name: '',
        position: '',
      };
      this.showModal = false;
    },
  },
};
</script>

<style>
/* Modal styles */
.modal {
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.4);
}
.modal-content {
  background-color: #fefefe;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 30%;
}
.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}
.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
table {
  width: 100%;
  border-collapse: collapse;
}
th,td {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
  background: #FFFFFF;
  text-align: center;
}
th {
  background-color: #f2f2f2;
  text-align: center;
}
h2{
  color: #FFFFFF;
  font-size: 32px;
}
</style>