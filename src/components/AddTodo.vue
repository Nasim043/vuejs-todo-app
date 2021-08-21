<template>
  <div>
    {{ title }}
    <form @submit="addTodo">
      <input type="text" v-model="title" placeholder="Add todo item" />
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import { uuid } from "vue-uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodoObj = {
        id: uuid.v4(), // create random id
        title: this.title,
        isCompleted: false,
      };
      this.$emit("add-todo", newTodoObj);
      this.title = "";
    },
  },
};
</script>

<style></style>
