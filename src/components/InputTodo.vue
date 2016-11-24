<template lang="html">
  <div class="wrapper">
    <!--<div class="container">-->
    <!--<input type="text" placeholder="Insert todo..." class = "input" autofocus>-->
    <div class="container card is-desktop is-mobile is-fullwidth">
      <div class="card-content">
        <div class="content">
          <!--<a href="#" @click="onOpenInputText"><span>+ Add</span></a>-->
          <div class="columns is-mobile">
            <div class="column is-8">
              <!--<input type="text" class="input is-fullheight is-fullheight" autofocus>-->
              <input type="text" v-model="todoInput" class="input" placeholder="Insert todo..." @keyup.enter="addTodo(todoInput),todoInput=''"
                autofocus>
            </div>
            <div class="column">
              <!--<input type="text" class="input is-fullheight is-fullheight">-->
              <div class="button is-pulled-right" @click="addTodo(todoInput),todoInput=''">Add</div>
            </div>
            <div class="column">
              <!--<input type="text" class="input is-fullheight is-fullheight">-->
              <div class="button is-pulled-right" @click="onCloseInput">Cancel</div>
            </div </div>
          </div>
        </div>
      </div>
      <!--</div>-->
    </div>
</template>

<script>
export default {
  props:['addTodo','onCloseInput'],
  data () {
    return {
      modalActive:false,
      fadeOut:'',
      todoInput:'',
    }
  },
  computed: {},
  mounted () {},
  methods: {
  },
  components: {
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