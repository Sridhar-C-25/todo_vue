<template>
   <div class="list" :class="{'complete' : todo.isComplete}">
       <input type="checkbox" @change="markComplete">
       <p>{{todo.title}}</p>
       <span @click="$emit('del-todo',todo.id)">x</span>
   </div>
</template>

<script>
export default {
    name:'Todo',
    props:['todo'],
    methods:{
        markComplete(){
            this.todo.isComplete = !this.todo.isComplete
        },
       
    }
}
</script>


<style scoped>
    .list{
        display: flex;
        align-items: center;
        justify-content: center;
        background: #f4f4f4;
        margin: 5px 0;
    }
    p{
       
        padding: 7px;
        font-size: 1.2rem;
    }
    span{
        cursor: pointer;
        position: absolute;
        right: 40px;
        background: #ff0000;
        color:#fff;
        padding: 5px 10px;
        border-radius: 50%;
    }
    .complete{
        text-decoration: line-through;
    }
</style>