<template>
  <div id="app">
    <div class="header">
      <div class="wrapper">
        <div class="title">Todolist</div>
      </div>
    </div>
    <MainArea></MainArea>
  </div>
</template>

<script>
  import MainArea from "./components/project/MainArea"
  export default {
    name: 'app',
    components:{
      MainArea
    }
  }

</script>
<style>
  @import "assets/css/base.css";
  .header{
    background-color: #e83629;
    height: 60px;
    width: 100%;
  }
  .title{
    line-height: 60px;
    text-align: center;
    color: #fff;
    font-size: 30px;
  }

</style>
