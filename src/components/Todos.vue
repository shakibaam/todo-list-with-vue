<template>
    <div>

        <h1>Todos</h1>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo"></TodoItem>

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
        }
    }
</script>

<style scoped>

</style>