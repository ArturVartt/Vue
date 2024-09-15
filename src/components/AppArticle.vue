<script setup lang="ts">
import type { Data } from '@/types'

defineProps<Data>()

const emit = defineEmits<{
  delete: [id: number]
}>()

function onClick(id: number) {
  emit('delete', id)
}
</script>

<template>
  <article class="article">
    <h2 class="title">{{ title }}</h2>
    <time class="time">{{ time }}</time>
    <button @click="onClick(id)" class="delete__btn">удалить</button>
  </article>
</template>

<style scoped>
.article {
  width: 100%;
  padding: 10px 0;
  border: 1px solid rebeccapurple;
  position: relative;
  min-height: 100px;
  max-width: 300px;
}
.title {
  text-align: center;
  font-size: 25px;
  font-weight: 600;
}

.time {
  font-size: 20px;
  position: absolute;
  bottom: 10px;
  right: 10px;
}
.delete__btn {
  border: 1px solid red;
  border-radius: 5px;
  padding: 5px;
  background: rgb(252, 235, 235);
  position: absolute;
  bottom: 10px;
  left: 10px;
}
</style>
