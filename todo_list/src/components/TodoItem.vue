<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}" @click="$emit('complete-todo')">
        <h3 class="title">{{ todo.title }}<button @click="$emit('delete-todo', todo.id)" class="del">x</button></h3>
        <p class="description">{{ todo.desc }}</p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props:["todo"],
}
</script>

<style scoped>
    .todo-item{
        background: #f4f4f4;
        border-bottom: 2px #ccc dotted;
    }

    .is-complete {
        background: #59ff53;
        text-decoration: line-through;
        color: #38a834;
    }

    .del {
        background: none;
        color: rgba(0, 0, 0, 0.5);
        border: none;
        border-radius: 50%;
        cursor: pointer;
        float: right;
        font-size: 20px;
    }

    .title{
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        border: none;
        text-align: left;
        text-transform: uppercase;
    }

    .description {
        text-align: left;
    }
</style>