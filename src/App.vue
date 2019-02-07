<template>
  <div id="app">
    {{msg}}
    <Todos v-bind:todos="todos"/>
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos.vue'


export default {
  name: 'app',
  components: {
     Todos
  },
  data(){
    return {
      todos:[
        {
          id:1,
          title:"test",
          complete:true
        },
        {
          id:2,
          title:"test12",
          complete:true
        },
        {
          id:3,
          title:"testeeee",
          complete:false
        }
      ],
      msg:"My first TodoList by Vue"
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
