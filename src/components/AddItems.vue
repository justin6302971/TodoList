<template>
   <div>
       <form @submit="addTodo">
        <input type="text" v-model="title" name="title" placeholder="add Todos ...">
        <input type="submit" class="btn" value="Submit">
       </form> 
   </div>
</template>

<script>
    import uuid from 'uuid';
    export default {
        name:"AddItems",
        data(){
            return{
                title: ''
            }
        },
        methods:{
            addTodo(e){       
                e.preventDefault();
                const newTodo={
                    id:uuid.v4(),
                    title:this.title,
                    completed:false
                }
                this.title="";
                this.$emit('add-todo',newTodo);
            }
        }
    }
</script>

<style scoped>
form{
    display: flex;
}
input[type="text"]{
    flex: 10;
    padding: 5px;

}

input[type="submit"]{
    flex:2;
}
</style>
