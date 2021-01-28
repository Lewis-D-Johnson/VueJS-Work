<template>
    <div class="Todo">
        <h2 class="TodoTitle">Todo List<button class="plus">+</button></h2>
        <div class="TodoBody">
            
        </div>
    </div>
</template>

<script>
export default {
  name: 'Todo',
  props: {
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.Todo{
    width: 100%;
    height: 80%;
    border-radius: 20px 20px 20px 20px;
    box-shadow: 0px 0px 10px #999999;
}
.TodoTitle{
    background: #5bee67;
    color: #000000;
    width: 100%;
    padding: 5px 0px 5px 0px;
    border-radius: 20px 20px 0px 0px;
}
.TodoBody{
    height: 300px;
    border-radius: 0px 0px 20px 20px;
}
.plus{
    float: right;
    background: none;
    border: none;
    font-size: 20px;
    width: 30px;
    height: 30px;
    margin: 0px 5px 0px 0px;
}
</style>