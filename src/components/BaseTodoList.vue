<template>
  <ul class="mw-768px text-align-left mg-auto mgt-24px">
    <li
      v-for="(todo, index) in todos"
      :key="index">
      {{ todo }}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'BaseTodoList',
  props: {
    todos: {
      type: Array,
      default: () => ([])
    }
  }
}
</script>
