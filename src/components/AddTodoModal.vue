<template>
    <div class="modal" id="todo-modal" v-bind:class="{ 'is-active animated fadeIn': modalActive,fadeOut}">
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
</template>
<script>
export default {
   props: ['onCloseModal','fadeOut','modalActive'],
    data () {
        return {}
    },
    computed: {},
    mounted () {
      console.log("",this.modalActive)
    },
    methods: {},
    components: {}
}
</script>
<style scoped>
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