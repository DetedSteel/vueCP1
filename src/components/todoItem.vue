<template>
  <div @click="changeStatus" :class="isComplete ? 'todo active' : 'todo'">
    {{ name }}
  </div>
</template>

<script setup>
import { ref } from 'vue'

let props = defineProps({
  name: String,
  isDone: Boolean
})

let isComplete = ref(props.isDone)

function changeStatus(e) {
  e.stopPropagation()

  isComplete.value = !isComplete.value
}
</script>

<style scoped>
.todo {
  padding: 10px 30px;
  background-color: red;
  width: 100%;
  margin-bottom: 10px;
  border-radius: 6px;
}

.active {
  background-color: green;
}
</style>
