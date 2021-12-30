<template>
  <div class="home">
    <h1>TODO TODO</h1>
    <AddTodo @add-todo ="addTodo"/>
    <Todos :todos="todos" @del-todo ="delTodo" />
  </div>
</template>

<script>
import Todos from '../components/Todos.vue'
import AddTodo from '../components/AddTodo.vue'

export default {
  name: 'Home',
  components:{
    Todos,
    AddTodo
  },
  methods:{
    delTodo(id){
      if(confirm('are you sure?')){
        this.todos = this.todos.filter(todo=>todo.id !== id)
      }
    },
    addTodo(newTodo){
      this.todos = [...this.todos,newTodo]
    }
  },
  data(){
    return{
     todos:[
      {
        title:'Todo 1',
        id:1,
        isComplete:false
      },
      {
        title:'Todo 2',
        id:2,
        isComplete:true
      },
      {
        title:'Todo 3',
        id:3,
        isComplete:false
      }
     ]
    }
  }
}
</script>
