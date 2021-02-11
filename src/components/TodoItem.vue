<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">


        <p>
            <input type="checkbox" v-on:change="markComplete">

            {{todo.title}}
            <button class="del">remove</button>

        </p>

    </div>
</template>

<script>

    export default {
        name: "TodoItem",
        props: ["todo"],
        methods: {
            markComplete() {
                this.todo.completed = !this.todo.completed;
            }
        }

    }
</script>

<style scoped>

    .todo-item {
        background-color: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #cccccc dotted;

    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: deeppink;
        border-radius: 50%;
        text-align: center;
        padding: 5px;
        position: absolute;
        right: 150px;
        border:deeppink ;
        color: white;
        transition: 0.3s;

    }
    button:hover{
        background: orchid;
    }



</style>