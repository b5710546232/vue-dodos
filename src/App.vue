<template>
  <div id="app">
    <Navbar :addTodo="addTodo" :onInput="onInput"></Navbar>
    <div class="container wrapper-body">
      <InputTodo id="todo-input" v-if="inputActive" :class="{ 'animated fadeIn': inputActive,fadeOut}" :onCloseModal="onCloseModal"
        :addTodo="addTodo" :fadeOut="fadeOut" :modalActive="true">
      </InputTodo>
      <TodoList id="todo-list" :todos="todos" :isEditMode="isEditMode"></TodoList>
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
        event.preventDefault()
        console.log('addTodo',value);
          let todo = {
          id: 0,
          title: value,
          completed: false
        }
      this.todos.push(todo)
        console.log('todos',this.todos);
        
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
      onCloseModal(){
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