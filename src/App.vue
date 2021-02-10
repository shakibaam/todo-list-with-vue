<template>
  <div id="app">
  <Todos v-bind:todos="todos"></Todos>

  </div>
</template>

<script>
  import Todos from './components/Todos'

export default {
  name: 'App',
  components: {
     Todos
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
