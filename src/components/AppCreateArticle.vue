<script setup lang="ts">
import { ref } from 'vue'

const valueInput = ref('')

const emit = defineEmits<{
  createArticle: [valueInput: string]
}>()

function onSubmit() {
  emit('createArticle', valueInput.value)
}
</script>

<template>
  <form @submit.prevent="onSubmit">
    <input class="input" type="text" v-model="valueInput" />
    <button class="button" type="submit">Создать карточку</button>
  </form>
</template>

<style scoped>
form {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.input {
  padding: 5px;
  border: 1px solid;
  font-size: 20px;
}
.button {
  padding: 5px;
  border: 1px solid;
  font-size: 20px;
}
</style>
