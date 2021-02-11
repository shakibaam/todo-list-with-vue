<template>
  <div id="app">
    <Header></Header>
    <AddTodo v-on:add-todo="addTodo"></AddTodo>
  <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"></Todos>




  </div>
</template>

<script>
  import Todos from './components/Todos'
  import Header from "./layout/Header";
  import AddTodo from "./components/AddTodo";


export default {
  name: 'App',
  components: {
     Todos,
    Header,
    AddTodo


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

    } ,
    addTodo(newTodo){
      this.todos=[...this.todos,newTodo];
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

  .btn{
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
    transition: 0.3s;
  }

  .btn:hover{

    background: #666;

  }
</style>
