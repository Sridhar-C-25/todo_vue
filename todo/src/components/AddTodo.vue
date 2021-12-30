<template>
    <div>
        <input type="text" v-model="title"  name="title" >
        <input type="submit" value="Add Todo.." @click="addTodo">
        
    </div>
</template>

<script>
export default {
    name:'AddTodo',
    data(){
        return{
            title:''
        }
    },
    methods:{
        addTodo(){
             if(this.title !== ''){
                 const newTodo ={
                id:Math.random()*10000,
                title:this.title,
                complete:false
            
             }
              this.$emit('add-todo',newTodo)
            this.title =''
             }
            //send to the parent
           
            
        }
    }
}
</script>

<style scoped>
    div{
        display: flex;
        width:100%;
        padding: 0 10px;
    }
    input{
        border-radius: 0;
        outline: none;
        font-family: inherit;
    }
    input:first-child{
        flex-basis: 80%;
        padding: 6px 0;
        border:1px solid #222;
    }
    input:last-child{
        flex-basis: 20%;
        background: #000;
        color: #fff;
        border:0;
    }
</style>