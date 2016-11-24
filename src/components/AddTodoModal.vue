<template>
    <div class="modal" id="todo-modal" v-bind:class="{ 'is-active animated fadeIn',fadeOut}">
      <div class="modal-background"></div>
      <div class="modal-card">
        <header class="modal-card-head">
          <p class="modal-card-title">Add todo</p>
          <button class="delete" @click="onCloseModal"></button>
        </header>
          <div class="modal-card-body">
          <!-- Content ... -->
          <input type="text" v-model="todoInput" class="input" placeholder="Insert todo..."
             @keyup.enter="addTodo(todoInput),todoInput=''" autofocus>

        </div>
        <footer class="modal-card-foot">
          <a class="button save-button" @click="addTodo(todoInput),todoInput=''" >Add</a>
          <a class="button cancel-button">Cancel</a>
        </footer>
      </div>
      <!-- Any other Bulma elements you want -->
    </div>
</template>
<script>
export default {
  //  props: ['onCloseModal','fadeOut','modalActive','addTodo'],
    data () {
        return {
          todoInput:''
        }
    },
    computed: {},
    mounted () {
      console.log("active",this.modalActive)
    },
    methods: {},
    components: {}
}
</script>
<style scoped>
.modal{
  z-index: 9999999;
}
  #todo-modal {
    animation-duration: 0.5s;
  }
    .save-button {
    background: rgb(135, 197, 243);
  }
  
  .cancel-button {
    background: rgb(92.1%, 58.9%, 58.9%)
  }
</style>