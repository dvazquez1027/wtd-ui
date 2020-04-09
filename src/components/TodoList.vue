<template>
  <div>
      <div :key="todo.id" v-for="todo in todos">
          <TodoItem :todo="todo" @del-todo="deleteTodo" />
      </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue"

export default {
  name: "TodoList",
  components: {
      TodoItem
  },
  props: ["todos"],
  methods: {
    deleteTodo(id) {
      this.$emit('del-todo', id);
    }
  }
};
</script>

<style scoped>
</style>