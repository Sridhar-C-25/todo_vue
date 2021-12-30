<template>
    <div v-for="todo in todos" :key="todo.id">
        <Todo :todo = "todo" v-on:del-todo ="$emit('del-todo',todo.id)"/>
    </div>
</template>

<script>
import Todo from './Todo.vue'
export default {
    name:'Todos',
    props:['todos'],
    components:{
        Todo
    },
    emits:['del-todo']
   
}
</script>
