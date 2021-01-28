<template>
  <div class="headerbar">
    <h1 class="title">ENTS AND EVENTS</h1>
  </div>
  <Sidebar v-on:show-home="showHome" v-on:show-calendar="showCalendar" v-on:show-clients="showClients" v-on:show-employees="showEmployees" v-on:show-subs="showSubs" v-on:show-inventory="showInventory"/>
  <Main v-bind:show-home="homeOpen" v-bind:show-calendar="calendarOpen" v-bind:show-clients="clientsOpen" v-bind:show-employees="employeesOpen" v-bind:show-sub-contractors="subsOpen" v-bind:show-inventory="inventoryOpen"/>
</template>

<script>
import Sidebar from './Sidebar.vue'
import Main from './Main.vue'

export default {
  name: 'Layout',
  created(){
    this.homeOpen = true;
  },
  data() {
    return {
      homeOpen: false,
      calendarOpen: false,
      clientsOpen: false,
      employeesOpen: false,
      subsOpen: false,
      inventoryOpen: false,
    }
  },
  components: {
    Sidebar, Main
  },
  props: {
  },
  methods: {
    showHome() {
      this.homeOpen = true;
      this.calendarOpen = false;
      this.clientsOpen = false;
      this.employeesOpen = false;
      this.subsOpen = false;
      this.inventoryOpen = false;
    },  
    showCalendar() {
      this.homeOpen = false;
      this.calendarOpen = true;
      this.clientsOpen = false;
      this.employeesOpen = false;
      this.subsOpen = false;
      this.inventoryOpen = false;
    },  
    showClients() {
      this.homeOpen = false;
      this.calendarOpen = false;
      this.clientsOpen = true;
      this.employeesOpen = false;
      this.subsOpen = false;
      this.inventoryOpen = false;
    },
    showEmployees() {
      this.homeOpen = false;
      this.calendarOpen = false;
      this.clientsOpen = false;
      this.employeesOpen = true;
      this.subsOpen = false;
      this.inventoryOpen = false;
    },
    showSubs() {
      this.homeOpen = false;
      this.calendarOpen = false;
      this.clientsOpen = false;
      this.employeesOpen = false;
      this.subsOpen = true;
      this.inventoryOpen = false;
    },
    showInventory() {
      this.homeOpen = false;
      this.calendarOpen = false;
      this.clientsOpen = false;
      this.employeesOpen = false;
      this.subsOpen = false;
      this.inventoryOpen = true;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.headerbar {
  height: 100%;
  background-color: #F0C808;
  box-shadow: 0px -1px 10px #999999;
}
.title{
  height: 50px;
  font-size: 32px;
  color: white;
	-webkit-text-stroke: 1px black;
  text-align: left;
  padding: 5px 0px 3px 15px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
</style>