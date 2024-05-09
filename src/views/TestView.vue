<template>
  <div>
    <div v-if="loading">Loading...</div>
    <div v-else>
      <p>{{ saveData.ID }}</p>
      <p>{{ saveData.Name }}</p>
      <p>{{ saveData.status }}</p>
      <p>{{ saveData.location }}</p>
      <p>{{ saveData.locations }}</p>
      <p>{{ saveData.Type }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      requestData: '',
      saveData: {},
      loading: false
    };
  },
  mounted() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      axios.get('http://localhost/phpchatbot/test.php')
        .then(response => {
          this.requestData = response.data;
          var lines = this.requestData.split("<br>");

          // Initialize an object to store key-value pairs
          console.log(lines);
          this.saveData = {
          ID : lines[0],
          Name : lines[1],
          status : lines[2],
          location : lines[3],
          locations : lines[4],
          Type : lines[5],
          }
          console.log(this.saveData);
        })
        .catch(error => {
          console.error('Error fetching data:', error);
          this.loading = true;
        });
    }
  }
}
</script>
