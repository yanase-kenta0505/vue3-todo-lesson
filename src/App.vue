<script setup lang="ts">
import { StringDecoder } from 'string_decoder';
import { ref } from 'vue';
import Test from './components/Test.vue'

const todos: string[] = []
let todo = ref<string>('')


const callTodo = () => {
  if (todo.value === '') return
  console.log(todo.value)
  todo.value = ''
}

let str = ref<String>('hello')

const foo = (mes: String) => {
  str.value = mes
}



</script>

<template>
  <div>
    <h1 class="w-300px bg-red-300 mx-auto mt-4 text-center text-2xl">your todo list</h1>
    <div class="flex justify-center mt-5">
      <input class="input input-primary w-300px" type="text" v-model="todo" />
      <button class="btn btn-primary ml-5" @click="callTodo">Button</button>
    </div>

    <Test @changeMes="foo" />
    <p class="w-200px mx-auto">{{str}}</p>
  </div>
</template>

