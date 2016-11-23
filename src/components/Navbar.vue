<template>
  <div class="wrapper">
    <div class="nav has-shadow is-info">
      <div class="nav-center is-active">
        <div class="columns is-mobile is-fullwidth">
          <div class="column is-10">
            <div class="nav-item title">Todo</div>
          </div>
          <div class="column">
            <div class="add-button has-text-right">
              <a class="fa fa-pencil-square-o fa-4x nav-item" @click="onOpenModal"></a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <AddTodoModal :onCloseModal="onCloseModal" :addTodo="addTodo" :fadeOut="fadeOut" :modalActive="modalActive"></AddTodoModal>
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
      console.log('open');      
      this.modalActive = true
    }
  },
  components:{
    AddTodoModal
  }
  
}
</script>
<style scoped>
  .wrapper {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 50px;
    z-index: 9999;
    margin: 0px auto;
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
  
  a:hover {
    color: white;
  }
</style>