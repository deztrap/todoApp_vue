<template>
  <div id="app">
    <input type="text" placeholder="Enter todo Item" v-model="inputTodo" />
    <button @click="addTodo">Add</button>
    <inputItem
      v-for="(todo, index) in todos"
      :key="index"
      :todoItem="todo"
      :todoItemIndex="index"
      @deleteMe="deleteTodo"
      @updateMe="updateTodo"
    />
  </div>
</template>

<script>
import InputItem from "./components/InputItem.vue";

export default {
  name: "App",
  components: {
    InputItem,
  },
  data: function () {
    return {
      todos: [],
      inputTodo: "",
    };
  },
  methods: {
    addTodo() {
      this.todos.push(this.inputTodo);
      this.inputTodo = "";
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
    updateTodo(name, index) {
      this.todos.splice(index, 1, name);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  margin-top: 60px;
}
</style>
