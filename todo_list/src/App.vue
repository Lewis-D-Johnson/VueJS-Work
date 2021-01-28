<template>
  <div id="app">
    <Layout v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-bind:completed-todos="completedTodos" v-on:complete-todo="completeTodo" v-on:delete-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todo'
import Layout from './components/Layout'
import uuid from 'uuid';

export default {
  name: 'App',
  components: {
    Todos,
    Layout
  },
  beforeMount(){
    this.updateTodos();
  },
  data() {
    return {
      todos: [],
      completedTodos: [],
      allTodos: [
        {
          id: uuid.v4(),
          title: 'Task 1',
          desc: 'hello task 1',
          completed: false
        },
        {
          id: uuid.v4(),
          title: 'Task 2',
          desc: 'hello task 2',
          completed: false
        },
        {
          id: uuid.v4(),
          title: 'Task 3',
          desc: 'hello task 3',
          completed: false
        }
      ]
    }
  },
  methods: {
    completeTodo(id) {
      for(let i = 0; i < this.allTodos.length; i++){
        if(this.allTodos[i].id == id){
          this.allTodos[i].completed = !this.allTodos[i].completed;
        }
      }
      this.updateTodos();
    },
    deleteTodo(id) {
      this.allTodos = this.allTodos.filter(todo => todo.id !== id);
      this.updateTodos();
    },
    updateTodos(){
      this.todos = this.allTodos.filter(todo => todo.completed === false);
      this.completedTodos = this.allTodos.filter(todo => todo.completed === true);
    },
    addTodo(todo){
      this.allTodos = [...this.allTodos, todo];
      this.updateTodos();
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
  margin-left: auto;
  margin-right: auto;
  width: 500px;
}
</style>
