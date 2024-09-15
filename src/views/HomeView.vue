<script setup lang="ts">
import AppArticle from '@/components/AppArticle.vue'
import AppCreateArticle from '@/components/AppCreateArticle.vue'
import type { Data } from '@/types'
import { ref } from 'vue'

const data = ref<Data[]>([
  { title: 'Hello1', time: '12/12/42', id: 1 },
  { title: 'Hello2', time: '13/64/43', id: 2 },
  { title: 'Hello3', time: '15/22/63', id: 3 },
  { title: 'Hello4', time: '12/43/42', id: 4 },
  { title: 'Hello5', time: '11/34/23', id: 5 }
])

function createNewArticle(title: string) {
  data.value.push({
    title: title,
    time: Date.now().toString(),
    id: Math.random() * 1000
  })
}

function deleteArticle(id: number) {
  const indexDeleteElement = data.value.findIndex((el) => el.id === id)
  data.value.splice(indexDeleteElement, 1)
}
</script>

<template>
  <AppCreateArticle @createArticle="createNewArticle" />
  <ul>
    <li v-for="item in data" :key="item.id">
      <AppArticle :title="item.title" :time="item.time" :id="item.id" @delete="deleteArticle" />
    </li>
  </ul>
</template>

<style scoped>
ul {
  width: 100%;
}
li {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}
</style>
