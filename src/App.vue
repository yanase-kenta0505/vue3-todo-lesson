<script setup lang="ts">
import { ref } from 'vue';
import DeleteBtn from './components/deleteBtn.vue';

const todos = ref<string[]>([])
let todoItem = ref<string>('')


const addTodo = () => {
  if (todoItem.value === '') return

  todos.value.push(todoItem.value)
  todoItem.value = ''
}

const deleteItem = (index: number) => {
  console.log(index)
  todos.value.splice(index, 1)
}



</script>

<template>
  <div>
    <h1 class="w-300px mx-auto mt-4 text-left text-3xl">your todo list</h1>
    <div class="flex justify-center mt-5">
      <input class="input input-primary w-300px" type="text" v-model="todoItem" />
      <button class="btn btn-primary ml-5" @click="addTodo">Add</button>
    </div>
    <ul class="w-400px mx-auto mt-5">
      <li
        v-for="(todo, index) in todos"
        :key="index"
        class="text-2xl mb-5 border-solid border-gray-500 border rounded-2xl p-5px flex items-center"
      >
        <span>・</span>
        {{ todo }}
        <DeleteBtn class="ml-auto" :index='index' @delete-item="deleteItem"/>
      </li>
    </ul>
  </div>
</template>

