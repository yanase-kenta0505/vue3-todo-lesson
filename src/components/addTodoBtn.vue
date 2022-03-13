<script setup lang="ts">
const props = defineProps<{
  todoItem: string
}>()

const emit = defineEmits<{
  (event: 'addTodoItem', todoItem: string): void
}>()

</script>

<template>
  <div>
    <button class="btn btn-primary ml-5" @click="emit('addTodoItem', props.todoItem)">Add</button>
  </div>
</template>