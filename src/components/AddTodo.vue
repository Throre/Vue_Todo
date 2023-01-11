<template>
  <form class="add-todo" @submit.prevent="onSubmit">
    <input type="text" v-model="title" placeholder="Add what you need to do">
    <button class="create" type="submit">Create</button>
  </form>
</template>

<script>
export default {
    data() {
        return{
            title: ''
        }
    },
    methods: {
        onSubmit() {
            if(this.title.trim()) {
                const newTodo = {
                    id: Date.now(),
                    title: this.title,
                    completed: false
                }
                this.$emit('add-todo', newTodo)
                this.title = ""
            }
        }
    }
}
</script>

<style scoped>
    .add-todo {
        display: flex;
        justify-content: center;
        margin: 30px 0 30px 0;
        padding: 30px;
        box-sizing: border-box;
    }
    input {
        width: 500px;
        margin-right: 30px;
        padding-left: 15px;
        box-sizing: border-box;
        border-radius: 5px;
    }
    .create {
        width: 100px;
        height: 30px;
        background: rgb(113, 255, 100);
        border-radius: 5px;
        border: 1px solid grey;
        font-size: 15px;
        font-family: 'Roboto', sans-serif;
        color: black;
    }
</style>