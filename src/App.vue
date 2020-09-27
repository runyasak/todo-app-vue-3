<template>
  <div id="nav">
    <div class="container mg-auto">
      <h1>Todo App</h1>

      <label for="text">
        Add todo:
        <input
          id="text"
          type="text"
          v-model="text"
          @keyup.enter="addTodo(text)">
      </label>

      <ul class="todo-list text-align-left mg-auto mgt-24px">
        <li
          v-for="(todo, index) in todos"
          :key="index">
          {{ todo }}
        </li>
      </ul>

      <button
        @click="addTodo(text)"
        class="mgt-48px">
        Add Todo
      </button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'App',
  setup () {
    const text = ref('')
    const todos = ref([])

    const addTodo = (value) => {
      todos.value.push(value)
      text.value = ''
    }

    return { text, todos, addTodo }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.container {
  max-width: 1024px;
}

.todo-list {
  max-width: 768px;
}

.mg-auto {
  margin: auto;
}

.mgt-24px {
  margin-top: 24px;
}

.mgt-48px {
  margin-top: 48px;
}

.text-align-left {
  text-align: left;
}
</style>
