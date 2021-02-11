<template>
  <div id="app">
    <Header></Header>
  <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"></Todos>



  </div>
</template>

<script>
  import Todos from './components/Todos'
  import Header from "./layout/Header";


export default {
  name: 'App',
  components: {
     Todos,
    Header


  },
  data(){
    return{
    todos:[
      {
        id:1,
        title:"TODO one",
        completed:false
      },
      {
        id:2,
        title:"TODO tow",
        completed:true
      },
      {
        id:3,
        title:"TODO three",
        completed:false
      }
    ]
      ,
      msg:"hi from data"
    }
  }
   , methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(todo =>todo.id !==id)

    }
  }
}
</script>

<style>
*{
box-sizing: border-box;
  margin: 0;
  padding: 0;

}

  body{
    font-family: Arial;
    line-height: 1.4;
  }
</style>
