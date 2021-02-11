<template>
    <div class="container">
        <form @submit="addTodo">

            <input type="text" v-model="title" name="title" placeholder="Add todo">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>

    export default {
        name: "AddTodo"
        ,data(){
            return{
                title:''
            }
        } ,
        methods :{
            addTodo(e){
                e.preventDefault();

                const newTodo={
                    id:Math.random() ,
                    title:this.title,
                    completed:false
                }
                this.$emit('add-todo' , newTodo);
                this.title='';
            }
        }
    }
</script>

<style scoped>

    form {

        /*display: flex;*/
        margin-left: 600px;
        margin-top: 50px;
        /*width: 100px;*/
    }

    input[type="text"] {
        /*flex: 10;*/
        padding: 5px;
        border: 2px solid black;
        font-family: 'Rubik', sans-serif;
        outline: 0;
        transition: .2s;
        margin-top: 20px;
        /*border: midnightblue;*/
    }

    input[type="submit"] {
        /*flex: 2;*/
        padding: 12px 10px;
        border: 0;
        background: linear-gradient(to right, #de48b5 0%,#0097ff 100%);
        border-radius: 3px;
        margin-top: 10px;
        color: #fff;
        letter-spacing: 1px;
        font-family: 'Rubik', sans-serif;
        margin-left: 30px;
    }



</style>