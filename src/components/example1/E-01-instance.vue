<template>
  <div>Hello, {{ message }}</div>
</template>

<script lang="ts">
export default {
  name: 'E01Instance'
}
</script>

<script setup lang="ts">
import { ref } from 'vue'

const baseName = 'JiYu'
const message = ref(baseName)
</script>

<style scoped>
div {
  color: blue;
  font-size: 20px;
  font-weight: bold;
}
</style>
