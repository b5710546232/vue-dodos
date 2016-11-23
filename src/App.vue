<template>
  <div id="app">
    <Navbar  :addTodo="addTodo"></Navbar>
    <div class="wrapper-body">
    <InputTodo id="todo-input"></InputTodo>
    <TodoList id="todo-list" :todos="todos"></TodoList>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import InputTodo from './components/InputTodo.vue'
import TodoList from './components/TodoList.vue'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      todoInput:'',
      todos:[]
    }
  },
  methods:{
      addTodo(value){
        event.preventDefault()
        console.log('addTodo',value);
      
          let todo = {
          id: 0,
          title: value,
          completed: false
        }
      this.todos.push(todo)
        console.log('todos',this.todos);
        
      }
  },
  components:{
    Navbar,
    InputTodo,
    TodoList
  },
  mounted(){
          for(let i in [1,2,3,4,5,6,7,8]){
        console.log('i  = ',i)
          let todo = {
          id: 0,
          title: "a;lsdfjk;laskdfj",
          completed: false
        }
      this.todos.push(todo)
      }
  }
}
</script>

<style>
  .header{
     /*position: fixed;
     top: 0;
     left: 0;
     width: 100%;*/
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:50px;
  z-index: 9999;
  margin:0px auto;
  }
  .wrapper-body{
  margin-top:100px;
  }
  #todo-list {
    position: relative;
    z-index: 1;
  /*margin-top:100px;*/
  margin-right: 2%;
  padding:0 0 0 0;
  }
  #todo-input{
    margin-right: 4%;
  }
  #app {
    display: block;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    /*margin-top: 60px;*/
  }
  
  h1,
  h2 {
    font-weight: normal;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    display: inline-block;
    margin: 0 10px;
  }
  
  a {
    color: #42b983;
  }
  /*#input-todo{
  margin:1%
}*/
</style>