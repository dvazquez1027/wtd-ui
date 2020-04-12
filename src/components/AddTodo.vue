<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" placeholder="Enter title of new TODO..." />
      <input
        type="text"
        v-model="description"
        placeholder="Enter description of new TODO..."
      />
      <input type="submit" value="Add Todo" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
    name: "AddTodo",
    data() {
        return {
            title: '',
            description: ''
        };
    },
    methods: {
        addTodo(event) {
            event.preventDefault();
            this.$emit('add-todo', {
              title: this.title,
              description: this.description,
              completed: false
            });
            this.title = this.description = '';
        }
    }
}
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}

input[type="submit"] {
  flex: 2;
}
</style>