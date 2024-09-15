<script setup lang="js"></script>

<template>
  <main>
    <div class="container">
      <div class="container__inner">
        <RouterView />
      </div>
    </div>
  </main>
</template>

<style scoped>
.container {
  max-width: 1220px;
  padding: 0 10px;
  margin: 0 auto;
}
.container__inner {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
