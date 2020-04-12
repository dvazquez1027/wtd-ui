<template>
  <div id="app">
    <Header />
    <AddTodo @add-todo="addTodo" />
    <TodoList v-bind:todos="todoList" @del-todo="deleteTodo" />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import Header from "./components/layout/Header.vue";
import AddTodo from "./components/AddTodo.vue";

export default {
  name: "App",
  components: {
    TodoList,
    Header,
    AddTodo
  },
  data() {
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
    },
    addTodo(todo) {
      this.todoList.push(todo);
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

.btn {
  background-color: black;
  color: white;
  font-weight: bold;
  padding: 5px;
}
</style>
