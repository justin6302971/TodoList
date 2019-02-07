<template>
    <div>
       <div v-bind:key="todo.id" v-for="todo in todos">
           <TodoItems v-bind:todoData="todo" v-on:del-todoItem="$emit('del-todoItem',todo.id)"/>
       </div>
    </div>
</template>

<script>
import TodoItems from "./TodoItems.vue";
export default {
    name:"Todos",
    components:{
        TodoItems
    },
    props:["todos"]
}
</script>

<style scoped>

</style>
