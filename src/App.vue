<script setup>
import { ref, computed } from 'vue'

const itemList = ref({
  todo: [{ title: "test1" }, { title: "test2" }],
  inProgress: [],
  done: [],
})

const todoLength = computed(() => {
  return itemList.value.todo.length
})
const inProgressLength = computed(() => {
  return itemList.value.inProgress.length
})
const doneLength = computed(() => {
  return itemList.value.done.length
})
</script>

<template>
  <main>
    <div class="lengthWrapper">
      <div>Todo: {{ todoLength }}</div>
      <div>In Progress: {{ inProgressLength }}</div>
      <div>Done: {{ doneLength }}</div>
    </div>
    <div class="lengthWrapper">
      <div>
      <div v-for="item in itemList.todo">{{ item.title }}</div></div>
    </div>
  </main>
</template>

<style scoped>
.lengthWrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  column-gap: 16px;
}
</style>
