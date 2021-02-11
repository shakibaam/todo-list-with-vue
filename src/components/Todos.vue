<template>
    <div>

        <h1>Todos :</h1>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo' , todo.id)"></TodoItem>

        </div>
    </div>
</template>

<script>
    import TodoItem from "./TodoItem";

    export default {
        name: "Todos",
        props:["todos"],
        components:{
            TodoItem
        } ,
        methods:{

        }
    }
</script>

<style scoped>

    h1{
        font-family: "Comic Sans MS";
        margin-left: 240px;
        color: #0000CD;

    }

</style>