<template>
  <div class="wrapper">
    <div class="nav has-shadow is-info">
      <div class="nav-center is-active">
        <div class="columns is-mobile">
          <div class="column is-10">
            <div class="nav-item title">Todo</div>
          </div>
          <div class="column">
            <div class="add-button is-pulled-right">
              <a class="fa fa-pencil-square-o fa-4x nav-item" @click="onInput"></a>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>
<script>
export default {
  props: ['addTodo','onInput'],
  data(){
    return {}
  },
  methods:{

  },
  components:{}
  
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