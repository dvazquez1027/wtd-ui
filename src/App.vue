<template>
  <div id="app">
    <TodoList v-bind:todos="todoList" @del-todo="deleteTodo" />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    TodoList
  },
  data: function() {
    return {
      todoList: [
        {
          id: "1",
          title: "Mow the lawn",
          description: "Mow the front and back yards, pull weeds, edge the sidewalk.",
          completed: false
        },
        {
          id: "2",
          title: "Do groceries",
          description:
            "Go to Target, Wal-Mart and Winn Dixie.",
          completed: false
        },
        {
          id: "3",
          title: "Shave",
          description:
            "Save so we look nice before doing anything else.",
            completed: true
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todoList = this.todoList.filter(todo => todo.id !== id);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
