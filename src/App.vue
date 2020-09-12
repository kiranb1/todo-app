<template>
  <div id="app">
    <Header />
    <AddToDo v-on:add-todo="addTodo" />
    <TodoList v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import Header from "@/components/Header";
import AddToDo from "@/components/AddTodo";

export default {
  name: "App",
  components: {
    TodoList,
    Header,
    AddToDo,
  },
  data() {
    return {
      todos: [
        // Test data
        // {
        //   id: 1,
        //   title: "todo1",
        //   complete: false,
        // },
        // {
        //   id: 2,
        //   title: "todo2",
        //   complete: true,
        // },
      ],
    };
  },
  methods: {
    addTodo(todo) {
      const lastId =
        this.todos.length > 0 ? this.todos[this.todos.length - 1].id : 0;
      const id = lastId + 1;
      const newTodo = { ...todo, id };

      this.todos = [...this.todos, newTodo];
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>

<style>
body {
  font-family: Roboto, sans-serif;
}
</style>
