<template>
  <div id="nav">
    <div class="container mg-auto">
      <h1>Todo App</h1>

      <BaseFormInput
        label="Add todo:"
        v-model="text"
        @keyup.enter="addTodo(text)"
      />

      <BaseTodoList :todos="todos" />

      <button
        @click="addTodo(text)"
        class="mgt-48px">
        Add Todo
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

export const text = ref('')
export const todos = ref([])

export const addTodo = (value) => {
  todos.value.push(value)
  text.value = ''
}

export { default as BaseFormInput } from './components/BaseFormInput'
export { default as BaseTodoList } from './components/BaseTodoList'
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

.mw-768px {
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
