<template>
  <div class="add">
    <input class="input" type="text" @keydown="addHandle" />
  </div>
</template>

<script setup>
const emit = defineEmits(['add'])
function addHandle(e) {
  if (e.key == 'Enter') {
    emit('add', e.target.value)
  }
}
</script>

<style scoped>
.add {
  padding: 20px 0;
}

.input {
  padding: 10px 20px;
  border: 2px solid bisque;
  border-radius: 10px;
  outline: none;
}
</style>
