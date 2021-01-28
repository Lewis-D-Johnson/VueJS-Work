<template>
  <div>
    <h2 class="header">Task List</h2>
    <p class="desc">Below is a list of tasks that you can add or remove from.</p>
    <p class="error" v-if="error">You need to ensure you have a title and description for your task.</p>
    <div class="inputArea">
      <input class="titleInput" v-model="titleInputModel" type="text" placeholder="New Todo Title...">
      <textarea class="descInput" v-model="descInputModel" rows="3" placeholder="New Todo Description..."></textarea>
      <button v-on:click="createTodo" class="createTodo">Add Todo...</button>
    </div>
  </div>
</template>

<script>
import uuid from 'uuid';
export default {
  name: 'layout',
  data() {
    return {
      titleInputModel: '',
      descInputModel: '',
      error: false
    }
  },
  props: {
  },
  methods: {
    createTodo(){
      if(!this.titleInputModel || !this.descInputModel){
        this.error = true;
        return;
      }else{
        const newTodo = {
          id: uuid.v4(),
          title: this.titleInputModel,
          desc: this.descInputModel,
          completed: false
        }

        this.titleInputModel = '';
        this.descInputModel = '';

        this.$emit('add-todo', newTodo);
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header{
  color: #546b81;
  text-transform: uppercase;
}
.desc{
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  color: #91a7bd;
  font-size: 12px;
}
.titleInput{
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 12px;
  width: 75%;
  float: left;
}
.descInput{
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 12px;
  width:75.4%;
  resize: none;
  float: left;
}
.createTodo{
  height: 72px;
  width: 117px;
}
.error{
  color: red;
}
</style>
