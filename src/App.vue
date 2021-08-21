<template>
  <div>
    <Todos :todos="todos" @delete-todo="deleteTodo" />
    <AddTodo @add-todo="AddTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo.vue";

export default {
  name: "App",
  components: { Todos, AddTodo },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Go workout",
          isCompleted: true,
        },
        {
          id: 2,
          title: "Do laundry",
          isCompleted: false,
        },
        {
          id: 3,
          title: "Cook food",
          isCompleted: false,
        },
        {
          id: 4,
          title: "Clean up room",
          isCompleted: false,
        },
        {
          id: 5,
          title: "Finish work",
          isCompleted: false,
        },
      ],
    };
  },
  methods: {
    AddTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter((value) => value.id !== todoId);
    },
  },
};
</script>

<style></style>
