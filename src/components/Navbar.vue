<template>
  <div class="wrapper">

    <section class="hero">
      <div class="hero-body">
        <h1 class="title">
          To-do
        </h1>
      </div>
    </section>
    <div class="nav has-shadow is-info">
      <div class="nav-center"></div>
      <div class="nav-right nav-item">
        <div class="add-button">
          <a class="fa fa-pencil-square-o fa-5x" @click="onOpenModal"></a>
        </div>
      </div>
    </div>
<AddTodoModal :onCloseModal="onCloseModal" :addTodo="addTodo" 
:fadeOut = "fadeOut" :modalActive="modalActive"></AddTodoModal>
</div>
</template>
<script>
import AddTodoModal from './AddToDoModal.vue'
export default {
  props: ['addTodo'],
  data(){
    return {
      modalActive:false,
      fadeOut:'',
    }
  },
  methods:{
    onCloseModal(){
      console.log('modal')
      this.fadeOut = 'fadeOut'
      console.log(this.fadeOut)
      setTimeout(()=>{
        console.log('should-close')
        this.modalActive=false
        this.fadeOut = ''
      },500)
    },
    onOpenModal(){
      this.modalActive = true
    }
  },
  components:{
    AddTodoModal
  }
  
}
</script>
<style scoped>
  .hero {
    background: rgb(135, 197, 243);
  }
  
  .nav {
    background: rgb(135, 197, 243);
  }
  
  
  .title {
    font-size: 52px;
    color: white;
  }
  
  
  a {
    color: white;
  }
  
  .nav-item a{
  }
  .nav-right {
    align-self: right;
  }
  
  a:hover {
    color: white;
  }
</style>