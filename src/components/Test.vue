<script setup lang="ts">


// interface Props {
//   limit: number;
// }
// const props = defineProps<Props>();

// const props = defineProps<{
//   num: Number
// }>()

const emit = defineEmits<{
  (event: 'changeMes', mes: String): void
}>()


</script>

<template>
  <div class="mx-auto w-200px mt-5">
    <button class="btn btn-secondary w-40px h-40px" @click="emit('changeMes', 'hello world')">btn</button>
  </div>
</template>