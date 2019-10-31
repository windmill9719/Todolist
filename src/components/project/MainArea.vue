<template>
  <div class="main-area">
    <div class="main-wrapper">
      <div class="content item-bar">
        <input type="text" v-model.trim="input" @keydown.enter="onAdd" placeholder="'干点啥呢'" >
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
        if(this.input){
        this.todos.push({
            text: this.input,
            isDone: false
        });
        this.input = ''
        }
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
    height: 40px;
    border: 0;
    outline: none;
    background-color: inherit;
    font-size: 25px;
  }
  .item-bar .item-text {
    display: inline-block;
    text-align: center;
    font-size: 30px;
  }

  .content input,.item-bar .item-text{
    margin-left: 40px;
    margin-right: 40px;
  }

  .content input::placeholder{
    text-align: center;
  }


  .item-bar{
    display: flex;
    height: 60px;
    border-right: 2px solid;
    border-left: 2px solid;
    border-bottom: 2px solid;
    border-color: #999;
    border-radius: 2px;
    align-items: center;
  }

  .item-bar:first-child{
    background-color: #eee;
    border-top: 2px solid #999;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
  }

  .item-bar:last-child{
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
  }

  .item-bar input, .item-bar .item-text{
    flex: 10;
  }

  .item-bar button {
    flex: 1;
    height: 30px;
    border: 2px solid palevioletred;
    border-radius: 3px;
    margin-right: 15px;
    background-color: indianred;
    color: #ffffff;
  }



</style>