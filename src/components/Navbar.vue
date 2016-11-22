<template>
  <div class="wrapper">
    <section class="hero">
      <div class="hero-body">
        <h1 class="title">
          To-do
        </h1>
      </div>
    </section>
    <div class="nav has-shadow is-info nav-right is-active">
      <div class="nav-item">
        <div class="add-button">
          <a class="fa fa-pencil-square-o fa-5x" @click ="onOpenModal"></a>
        </div>
      </div>
    </div>
    <div class="modal" id="todo-modal"  v-bind:class="{ 'is-active animated fadeIn': modalActive , fadeOut}" >
 <div class="modal-background"></div>
  <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Add todo</p>
      <button class="delete" @click="onCloseModal"></button>
    </header>
    <div class="modal-card-body">
      <!-- Content ... -->
      <input type="text" class="input" placeholder="Insert todo..." autofocus>
    </div>
    <footer class="modal-card-foot">
      <a class="button save-button">Add</a>
      <a class="button cancel-button">Cancel</a>
    </footer>
  </div>
    <!-- Any other Bulma elements you want -->
  </div>
</div>
  </div>
</template>
<script>
export default {
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
      setTimeout(()=>{
        console.log('should-close')
        this.modalActive=false
        this.fadeOut = ''
      },500)
    },
    onOpenModal(){
      this.modalActive = true
    }
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
    color: white;
  }
  
  .nav-item {

    position: relative;
  }
  a{
  color: white;
}
.add-button{
  clear: both;
  float: right;
}
.save-button{
  background: rgb(135, 197, 243);
}
.cancel-button{
  background: rgb(92.1%, 58.9%, 58.9%)
}
.nav-right{
  clear:both;
}
  a:hover{
  color: white;
}
#todo-modal{
  animation-duration:0.5s;
}
</style>