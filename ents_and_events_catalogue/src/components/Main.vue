<template>
    <div class="divs">
        <div class="page" v-show="showHome">
            <div class="titleDiv">
                <img src="../assets/house.png" class="pageIcon" />
                <h1 class="pageTitle">HOME</h1>
            </div>
            <div class="section1">
                <Todo />
            </div>
            <div class="section2">
                <Schedule />
            </div>
        </div>

        <div class="page" v-show="showCalendar">
            <img src="../assets/schedule.png" class="pageIcon" />
            <h1 class="pageTitle">CALENDAR</h1>
        </div>

        <div class="page" v-show="showClients">
            <img src="../assets/customer-review.png" class="pageIcon" />
            <h1 class="pageTitle">CLIENTS</h1>
        </div>

        <div class="page" v-show="showEmployees">
            <img src="../assets/employee.png" class="pageIcon" />
            <h1 class="pageTitle">EMPLOYEES</h1>
        </div>

        <div class="page" v-show="showSubContractors">
            <img src="../assets/contract.png" class="pageIcon" />
            <h1 class="pageTitle">SUB-CONTRACTORS</h1>
        </div>

        <div class="page" v-show="showInventory">
            <img src="../assets/wholesaler.png" class="pageIcon" />
            <h1 class="pageTitle">INVENTORY</h1>
        </div>
    </div>
</template>

<script>
import Todo from './Todolist.vue'
import Schedule from './Schedule.vue'
export default {
  name: "Main",
  props: [
    "showHome",
    "showCalendar",
    "showClients",
    "showEmployees",
    "showSubContractors",
    "showInventory",
  ],
  components: {
      Todo, Schedule, 
  }
};
</script>
<style scoped>
.divs {
  background: #ffffff;
  width: 85vw;
  height: 94.89vh;
  z-index: -2;
  position: absolute;
  left: 14.99vw;
}
.page{
    width:100%;
    height:100%;
}
.titleDiv{
    width: 80vww;
    height: 200px;
}
.pageIcon {
    float: left;
    margin: 36px 0px 0px 50px;
}
.pageTitle {
    float: left;
    font-size: 60px;
    margin: 75px 0px 0px 15px;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
.section1{
    width: 45%;
    float:left;
    margin: 0px 0px 0px 50px;
}
.section2{
    width: 45%;
    float:right;
    margin: 0px 50px 0px 0px;
}
</style>