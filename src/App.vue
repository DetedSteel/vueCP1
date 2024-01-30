<script setup>
import AddTodo from './components/addTodo.vue'
import TodoList from './components/todoList.vue'
import { ref } from 'vue'
function add(title) {
  console.log(title)
  list.value.push({ id: Date.now(), name: title, isDone: false })
  console.log(list.value)
}

function deleteTodo(id) {
  list.value = list.value.filter((e) => e.id != id)
}

let list = ref([
  { id: 1, name: 'todo1', isDone: true },
  { id: 2, name: 'todo2', isDone: true }
])
</script>

<template>
  <div class="container">
    <add-todo @add="add"></add-todo>
    <todo-list :list="list" @deletetodo="deleteTodo"></todo-list>
  </div>
</template>

<style scoped>
* {
  font-family: sans-serif;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 300px;
  margin: 0 auto;
}
</style>
