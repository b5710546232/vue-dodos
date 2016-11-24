<template>
  <div id="app">
    <Navbar :addTodo="addTodo" :onInput="onInput"></Navbar>
    <div class="container wrapper-body">
      <InputTodo id="todo-input" v-if="inputActive" :class="{ 'animated fadeIn': inputActive,fadeOut}" :onCloseInput="onCloseInput"
        :addTodo="addTodo" :fadeOut="fadeOut">
      </InputTodo>
      <TodoList id="todo-list" :todos="todos" :isEditMode="isEditMode" :onCloseInput="onCloseInput" :removeToDo="removeToDo"></TodoList>
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
      todoInput:'',
      isEditMode:false,
      todos:[],
      inputActive:false,
      fadeOut: ''
    }
  },
  methods:{
      addTodo(value){
         if (event) event.preventDefault()
        console.log('addTodo',value);
          let timestamp = new Date().getUTCMilliseconds();
          let todo = {
          id: timestamp,
          title: value,
          completed: false
        }
        this.todos.push(todo)
        console.log('todos',this.todos);
        this.onCloseInput()
        
      },
      removeToDo(todo){
        this.todos.splice(this.todos.indexOf(todo), 1)
        
      },
      onInput(){
        if(this.inputActive){
          this.fadeOut = 'fadeOut'
          console.log('fade',this.fadeOut)
        setTimeout(()=>{
          this.inputActive = false
          this.isEditMode = false
          this.fadeOut = ''
        },300)
        }
        else{
          this.isEditMode = true
          this.inputActive = !this.inputActive
          console.log('sfa',this.inputActive)
        }
        
      },
      onCloseInput(){
        this.fadeOut = 'fadeOut'
        console.log(this.fadeOut)
        setTimeout(()=>{
          console.log('should-close')
          this.inputActive = false
          this.isEditMode = false
          this.fadeOut = ''
        },300)
    },
  },
  components:{
    Navbar,
    InputTodo,
    TodoList
  },
  mounted(){
          for(let i in [1,2,3,4,5,6,7,8]){
            console.log('i  = ',i)
            this.addTodo('Hello'+i)
          }
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
}
  .header {
    /*position: fixed;
     top: 0;
     left: 0;
     width: 100%;*/
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 50px;
    margin: 0px auto;
  }
  
  .wrapper-body {
    margin-top: 100px;
  }
  
  #todo-list {
    position: relative;
    /*z-index: 1;*/
    left: 0;
    /*margin-top:100px;*/
    /*margin-right: 2%;*/
    /*padding: 0 0 0 0;*/
  }
  
  #todo-input {
    /*margin-right: 4%;*/
    animation-duration: 0.3s;
  }
  
  #app {
    display: block;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    overflow: hidden;
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