<template>
  <div class="sidebar">
      <button type="button" class="homBtn" @click="$emit('show-home')">HOME</button>
      <button type="button" class="calBtn" @click="$emit('show-calendar')">CALENDAR</button>
      <button type="button" class="cliBtn" @click="$emit('show-clients')">CLIENTS</button>
      <button type="button" class="empBtn" @click="$emit('show-employees')">EMPLOYEES</button>
      <button type="button" class="subBtn" @click="$emit('show-subs')">SUB-CONTRACTORS</button>
      <button type="button" class="invBtn" @click="$emit('show-inventory')">INVENTORY</button>
      <button type="button" class="loginBtn" @click="$emit('login')">LOGIN</button>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  props: {
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.sidebar {
  background-color: #ffffff;
  width: 15vw;
  height: 94.9vh;
  position: absolute;
  z-index: -1;
  box-shadow: 0px -1px 5px #999999;
}
button{
    width: 100%;
    height: 50px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background:#ffffff;
    border: none;
    font-size: 14px;
    margin: 5px 0px 0px 0px;
}
button:hover{
    width: 100%;
    height: 50px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background:#ffffff;
    border: none;
    font-size: 20px;
}
button:focus{
    width: 100%;
    height: 50px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background:#45bae9;
    color: #ffffff;
    border: none;
    font-size: 20px;
    outline:none;
}
.loginBtn{
  position: absolute;
  bottom: 0px;
  left: 0px;
}
</style>