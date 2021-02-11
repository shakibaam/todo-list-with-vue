<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">


        <p>
            <input type="checkbox" v-on:change="markComplete">

            {{todo.title}}
            <button class="del" @click=deleteItem>remove</button>

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
            },
            deleteItem(){
                this.$emit('del-todo' , this.todo.id);
            }
        }

    }
</script>

<style scoped>

    .todo-item {
        background-color: #E0FFFF;
        padding: 10px;
        border-bottom: 1px #cccccc dotted;
        font-family: cursive;
        margin: auto;

        width: 70%;

    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #8A2BE2;
        border-radius: 50%;
        text-align: center;
        padding: 5px;
        position: absolute;
        right: 300px;
        /*left: 10px;*/
        border:#8A2BE2 ;
        color: white;
        transition: 0.3s;

    }
    button:hover{
        background: #4B0082;
    }



</style>