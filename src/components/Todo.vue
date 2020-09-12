<template>
  <li class="list-group-item" v-bind:class="{'todo-complete':todo.complete}">
    <input type="checkbox" v-on:change="toggleComplete" />
    {{ todo.title }}
    <button
      class="float-right border-0 bg-white"
      @click="$emit('delete-todo', todo.id)"
    >
      <i class="fas fa-trash"></i>
    </button>
  </li>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    toggleComplete() {
      this.todo.complete = !this.todo.complete;
    },
  },
};
</script>

<style scoped>
li {
  width: 50%;
  min-width: 500px;
  margin: 0 auto;
  color: #6c757d;
}

.todo-complete {
  text-decoration: line-through;
}

.list-group-item {
  border: none;
  border-bottom: 1px solid lightgray;
}

button {
  color: #f09;
}
</style>