<template>
  <div style="display: flex;">
    <div class="side-bar">
      <img src="https://maechanhospital.go.th/images/logo66.png" style="width: 100%; margin-top: 10px;" /><br><br>
      <nav>
        <router-link to="/"><i class="fa-solid fa-house"></i></router-link><br><br><br>
        
        <router-link to="/porter"><i class="fa-solid fa-user"></i></router-link><br><br><br>
        
        <router-link to="/time"><i class="fa-solid fa-file-lines"></i></router-link><br><br><br>
        
        <router-link to="/about"><i class="fa-solid fa-user-plus"></i></router-link>
      </nav>
    </div>
    <div style="padding: 15px; width: 100%;">
      <router-view />
    </div>
  </div>
  <link rel="stylesheet" type="text/css"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
</template>

<style>
body {
  margin: 0px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-image: -moz-linear-gradient(0deg, #CCFFFF 0%, #33CCFF 100%);
  background-image: -webkit-linear-gradient(90deg, #CCFFFF 0%, #33CCFF 100%);
  max-width: auto;
  height: auto !important;
}

nav {
  padding: 20px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: #33CCFF;
}

.side-bar {
  width: 150px;
  height: 100vh;
  background-color: #F5F5F5;
  text-align: center;
  /* position: absolute; */
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  border-radius: 12px;
}
.fa-solid {
        font-size: 30px; /* เปลี่ยนขนาดไอคอนตามต้องการ */
    }
</style>
