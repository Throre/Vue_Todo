<template>
  <div id="app">
    
    <AddTodo 
      @add-todo="addTodo"
    />

    <TodoList 
    v-bind:todos="todos"
    @remove-todo="removeTodo"
    />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList'
import AddTodo from '@/components/AddTodo'

export default {
  name: 'app',
  data() {
    return {
      todos: []
    }
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
  components: {
    TodoList,
    AddTodo
  }
}
</script>

<style>

#app {
  height: 700px;
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  background-image: url("https://img.freepik.com/free-vector/quote-background-design_1257-196.jpg?w=2000");
  background-repeat: no-repeat;
  background-position: top;
  background-size: 700px;
}
</style>
