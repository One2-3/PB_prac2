<template>
  <div>
    <p>{{ sharedMessage }}</p>
  </div>
</template>

<script lang="ts">
export default {
  name: 'ChildComponent2'
}
</script>

<script setup lang="ts">
import { inject } from 'vue'

const sharedMessage = inject<string>('sharedMessage', '')
</script>

<style scoped>
p {
  font-size: 1.5rem;
}
</style>
