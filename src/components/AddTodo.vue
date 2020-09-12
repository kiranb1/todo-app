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
        <button class="btn btn-outline-secondary" type="submit" id="button-addon2">Add</button>
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
input,
button {
  border-radius: 0;
}

button {
  background-color: #6c757d;
  border-color: #6c757d;
  color: white;
}

button:hover {
  background-color: #65676c;
  border-color: #65676c;
}

.form-control:focus {
  box-shadow: none;
}
</style>