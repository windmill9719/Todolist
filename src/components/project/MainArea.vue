<template>
  <div class="main-area">
    <div class="main-wrapper">
      <div class="content">
        <div>
          <input type="text" v-model="input" @submit.prevent>
          <button @click="onAdd">add</button>
          <button>more</button>
        </div>
        <ItemBar v-for="(todo, index) in todos" :key="index">{{todo.text}}</ItemBar>
      </div>
    </div>
  </div>
</template>

<script>
  import ItemBar from "./ItemBar";
  export default {
    name: "MainArea",
    components:{
      ItemBar
    },
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
      onSubmit(){

      }
    }
  }
</script>

<style scoped>
  .content input{
    width: 80%;
    height: 40px;
  }
</style>