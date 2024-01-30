<template>
  <todo-item
    v-for="e in list"
    :key="e.id"
    :name="e.name"
    :is-done="e.isDone"
    @dblclick="$emit('deletetodo', e.id)"
  ></todo-item>
</template>

<script setup>
import TodoItem from './todoItem.vue'

defineProps({
  list: Array
})
defineEmits(['deletetodo'])
</script>

<style></style>
