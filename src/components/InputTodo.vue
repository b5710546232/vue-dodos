<template lang="html">
  <div class="wrapper">
    <div class="container">
      <!--<input type="text" placeholder="Insert todo..." class = "input" autofocus>-->
      <div class="card is-desktop is-mobile is-fullwidth">
        <div class="card-content">
          <div class="content">
            <a href="#" @click="onOpenModal"><span>+ Add</span></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AddTodoModal from './AddToDoModal.vue'
export default {
  data () {
    return {
      modalActive:false,
      fadeOut:'',
    }
  },
  computed: {},
  mounted () {},
  methods: {
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
  components: {
    AddTodoModal
  }
}
</script>
<style scoped>
  .container {
    overflow: hidden;
  }
  
  
  .card {
    width: 100%;
    margin-bottom: 1%;
  }
</style>