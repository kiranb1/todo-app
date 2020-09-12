<template>
  <div>
    <ul class="list-group">
      <div v-bind:key="todo.id" v-for="todo in todos">
        <Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)" />
      </div>
    </ul>
  </div>
</template>

<script>
import Todo from "@/components/Todo";

export default {
  name: "TodoList",
  components: {
    Todo,
  },
  props: ["todos"],
};
</script>

<style scoped>
</style>