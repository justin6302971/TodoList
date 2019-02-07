<template>
    <div>
       <div v-bind:key="todo.id" v-for="todo in todos">
           <!-- {{todo.title}} -->
           <TodoItems v-bind:todoData="todo" />
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

<style>

</style>
