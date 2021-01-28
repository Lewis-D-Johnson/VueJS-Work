<template>
    <div class="Schedule">
        <h2 class="ScheduleTitle">Schedule</h2>
        <div class="ScheduleBody">
            
        </div>
    </div>
</template>

<script>
export default {
  name: 'Schedule',
  props: {
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.Schedule{
    width: 100%;
    height: 80%;
    border-radius: 20px 20px 20px 20px;
    box-shadow: 0px 0px 10px #999999;
}
.ScheduleTitle{
    background: #5beee7;
    color: #000000;
    width: 100%;
    padding: 5px 0px 5px 0px;
    border-radius: 10px 10px 0px 0px;
}
.ScheduleBody{
    height: 500px;
}
</style>