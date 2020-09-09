<template>
  <div class="todo-item" v-bind:class="{'is-complete': todo.completed}">
    <input type="checkbox" v-on:change="markComplete" :checked="todo.completed" />
    <span>{{todo.title}}</span>
    <button @click="$emit('del-todo', todo.id)" class="del">X</button>
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
  },
};
</script>

<style scope>
.todo-item {
  background-color: #fdd457;
  border-radius: 5px;
  margin-top: 10px;
  padding: 10px;
  transition: 0.3s ease;
}

.todo-item span {
  margin-left: 6px;
}

.is-complete {
  background-color: lightslategray;
  color: white;
  text-decoration: line-through;
  transition: 0.3s ease;
}

.del {
  background-color: #dc3545;
  border: none;
  border-radius: 5px;
  color: white;
  cursor: pointer;
  float: right;
  padding: 5px 9px;
}
</style>