<template>
  <div id="app" class="container">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "../components/Todos";
import AddTodo from "../components/AddTodo";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    // Delete
    deleteTodo(id) {
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(() => (this.todos = this.todos.filter((todo) => todo.id !== id)))
        .catch((err) => console.log(err));
    },

    // Add
    addTodo(newTodo) {
      const { title, completed } = newTodo;

      if (title) {
        axios
          .post("https://jsonplaceholder.typicode.com/todos", {
            title,
            completed,
          })
          .then((res) => {
            console.log(res);
            this.todos = [...this.todos, res.data];
          })
          .catch((err) => console.log(err));
      } else {
        alert("Field is empty!");
      }
    },
  },

  // Get list
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=10")
      .then((res) => (this.todos = res.data))
      .catch((err) => console.log(err));
  },
};
</script>

<style scoped>
</style>
