<template>
  <div>
    <h1>Todos list</h1>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <Todo :todo="todo" @delete-todo="$emit('delete-todo', todo.id)" />
      </li>
    </ul>
  </div>
</template>

<script>
import Todo from "./Todo.vue";
export default {
  name: "Todos",
  components: {
    Todo,
  },
  props: ["todos"],
};
</script>

<style></style>
