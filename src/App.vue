<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
    <AddTodo v-on:add-todo="addTodo"/>
  </div>
</template>
<script>
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';
export default {
  name: 'app',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Complete Vue',
          completed: false
        },
        {
          id: 2,
          title: 'Complete Solidity',
          completed: false
        },
        {
          id: 3,
          title: 'Learn Linear Regression',
          completed: false
        },
        {
          id: 4,
          title: 'Learn ASP.NET',
          completed: false
        },
        {
          i: 5,
          title: 'Complete project',
          completed: false
        }
      ],
    }
  },
  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    }
  }
}
</script>
<style scoped>
#app {
  background: rgb(229, 235, 205);
  
}
</style>