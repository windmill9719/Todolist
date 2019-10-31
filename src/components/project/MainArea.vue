<template>
  <div class="main-area">
    <div class="main-wrapper">
      <div class="content item-bar">
        <input type="text" v-model="input" @submit.prevent>
        <button @click="onAdd">add</button>
        <button>more</button>
      </div>
      <div v-for="(todo, index) in todos"
           :key="index"
           :class="{done: todo.isDone}" class="item-bar">
        <div class="item-text">{{todo.text}}</div>
        <button @click="onDone(index)">done</button>
        <button @click="onDelete(index)">delete</button>
      </div>

    </div>
  </div>
</template>

<script>
  // import ItemBar from "./ItemBar";
  export default {
    name: "MainArea",
    data(){
      return{
        input: '',
        todos:[
          {
            text: 'eat',
            isDone: false
          },
          {
            text: 'sleep',
            isDone: false
          },
          {
            text: 'sing',
            isDone: false
          }
        ]
      }
    },
    methods:{
      onAdd(){
        this.todos.push({
            text: this.input,
            isDone: false
        })
        this.input = ''
      },
      onDone(index){
        this.todos[index].isDone = ! this.todos[index].isDone;
      },
      onDelete(index){
        this.todos.splice(index,1)
      }
    }
  }
</script>

<style scoped>
  .content input{
    /*width: 80%;*/
    height: 30px;
    border: 0;
    outline: none;
  }


  .item-bar{
    display: flex;
    height: 50px;
    border: 2px solid #eee;
    margin-bottom: 2px;
    align-items: center;
  }

  .item-bar input, .item-bar .item-text{
    flex: 10;
  }

  .item-bar button {
    flex: 1;
    margin-right: 15px;
  }


  .item-bar .item-text {
    display: inline-block;
    text-align: center;
    width: 70%;
    font-size: 30px;
    list-style: none;
  }
</style>