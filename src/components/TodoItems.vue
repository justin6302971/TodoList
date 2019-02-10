<template>
    <div class="todo-item" v-bind:class="{'is-complete':todoData.completed}">
        <p>
           <input type="checkbox" v-bind:checked=todoData.completed v-on:change="markonComplete">
           {{todoData.title}}
        </p>
        <button @click="$emit('del-todoItem',todoData.id)" class="del">x</button>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props:["todoData"],
    methods:{
        markonComplete(){
            this.todoData.completed= !this.todoData.completed;
        }
    }
}
</script>

<style scoped>
.todo-item{
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
}

.is-complete{
    text-decoration: line-through;
}
.todo-item > button{
    position: relative;
    top: -18px;
    float: right;
}

.del{
    width:15px;
    background: #ff0000;
    color:#fff;
    border:none;
    border-radius: 50%;   
}
</style>
