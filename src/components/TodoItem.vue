<template>
  <div>
    <div class="todo-item" :class="{'is-complete':todo.completed}">
      <input type="checkbox" v-on:change="markComplete" :checked="todo.completed" />
      {{ todo.title }}
      <button class="del" @click="deleteTodo">x</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
    deleteTodo() {
      this.$emit('del-todo', this.todo.id);
    }
  }
};
</script>

<style scoped>
.todo-item {
  text-align: left;
  background-color: lightgrey;
  border-bottom: 1px darkgray dotted;
  padding: 10px;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  display: inline-block;
  border: none;
  background: red;
  color: white;
  float: right;
  padding: 5px 9px;
  border-radius: 50%;
}
</style>