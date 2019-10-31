<template>
  <div class="item-bar">
    <div class="item-text"><slot></slot></div>
    <button @click="onDone">done</button>
    <button>delete</button>
  </div>
</template>

<script>
  export default {
    name: "ItemBar",
    methods:{
      onDone(){
        this.$emit(onItemDone)
      }
    }
  }
</script>

<style scoped>
  .item-bar{
    height: 50px;
    border: 2px solid #eee;
    margin-bottom: 2px;
  }

  .item-bar .item-text {
    display: inline-block;
    text-align: center;
    width: 70%;
    font-size: 30px;
    list-style: none;
  }

</style>