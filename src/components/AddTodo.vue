<template>
  <form @submit.prevent="AddNewTodo">
    <div class="input-group mb-3">
      <input
        type="text"
        v-model="todo.title"
        class="form-control"
        placeholder="Add a to-do"
        aria-label="Add a to-do"
        aria-describedby="button-addon2"
      />
      <div class="input-group-append">
        <button class="btn btn-outline-secondary" type="button" id="button-addon2">Add</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      todo: {
        title: "",
        complete: false,
      },
    };
  },
  methods: {
    AddNewTodo() {
      if (this.title !== "") {
        this.$emit("add-todo", this.todo);

        this.todo = {
          title: "",
          complete: false,
        };
      }
    },
  },
};
</script>

<style scoped>
</style>