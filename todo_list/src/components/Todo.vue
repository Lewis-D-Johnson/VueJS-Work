<template>
    <div>
        <h2 v-if="false">New Task</h2>
        <h2 v-if="todos.length">In Progress</h2>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)" v-on:complete-todo="$emit('complete-todo', todo.id)"></TodoItem>
        </div>
        <h2 v-if="completedTodos.length">Completed</h2>
        <div v-bind:key="compTodo.id" v-for="compTodo in completedTodos">
            <TodoItem v-bind:todo="compTodo" v-on:delete-todo="$emit('delete-todo', compTodo.id)" v-on:complete-todo="$emit('complete-todo', compTodo.id)"></TodoItem>
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  components: { TodoItem },
    name: "Todos",
    props: ["todos", "completedTodos"],
}
</script>

<style scoped>

</style>