<template>
  <div id="app">
    <TodoList v-bind:todos="todos" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";

export default {
  name: 'App',
  components: {
    TodoList
  },
  data() {
    return {
      todos: [
        // Test data
        {
          id: 1,
          title: "todo1",
          complete: false
        },
        {
          id: 2,
          title: "todo2",
          complete: true
        }
      ]
    }
  }
}
</script>

<style>
  body {
    font-family: Roboto, sans-serif;
  }
</style>
