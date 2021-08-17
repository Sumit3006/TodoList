<template>
  <div v-bind:class="{ 'completed': todo.completed }" >
    <p v-on:click="markComplete">{{ todo.title }}</p>
    <button style="float:left;
    background: lightgrey;
    width: 100px;
    height:  20px;" @click="$emit('delete-todo', todo.id,)">Mark done!</button>
  </div>
</template>
<script>
export default {
  name: 'Todo',
  props: [
    "todo"
  ],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>
<style scoped>
  .completed {
    text-decoration: line-through;
    
  }
  #left{
    float: left;
    background: lightgrey;
    width: 100px;
    height:  20px;
}
</style>