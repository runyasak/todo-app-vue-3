<template>
  <label for="text">
    {{ label }}
    <input
      v-bind="$attrs"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
      @keyup.enter="$emit('enter-submit', $event.target.value)">
  </label>
</template>

<script>
export default {
  name: 'BaseFormInput',
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    }
  }
}
</script>
