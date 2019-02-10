<template>
  <div id="app">
    <Header/>
    <AddItems v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todoItem="deleteTodo"/>
    <Footer></Footer>
  </div>
</template>

<script>

import AddItems from './components/AddItems.vue';
import Todos from './components/Todos.vue';
import Header from './components/Layout/Header.vue';
import Footer from './components/Layout/Footer.vue';

export default {
  name: 'app',
  components: {
     Header,
     AddItems,
     Todos,
     Footer
  },
  data(){
    return {
      todos:[
        {
          id:1,
          title:"test",
          completed:true
        },
        {
          id:2,
          title:"test12",
          completed:true
        },
        {
          id:3,
          title:"testeeee",
          completed:false
        }
      ]
    }
  },
  methods:{
    addTodo(newTodo){

      this.todos=[...this.todos,newTodo]
    },
    deleteTodo(id){
      this.todos=this.todos.filter(i=>i.id!==id);
    }
  }
}
</script>

<style>
* {
 box-sizing: border-box;
 margin:0;
 padding: 0;

}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.btn{
  display: inline-block;
  border:none;
  background: #555;
  color:#fff;
  cursor: pointer;
  padding:7px 20px;
}
.btn:hover{
  background: #666;
}

</style>
