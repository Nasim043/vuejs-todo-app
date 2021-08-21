<template>
  <div :class="{ completed: todo.isCompleted }">
    <p @click="markComplete">{{ todo.title }}</p>
    <button @click="$emit('delete-todo', todo.id)">
      Delete
    </button>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.isCompleted = !this.todo.isCompleted;
    },
  },
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>
