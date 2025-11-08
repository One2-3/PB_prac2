<template>
  <div>
    <p>{{ message }}</p>
    <button @click="$emit('custom-event', 'Hello from child')">Send Event</button>
  </div>
</template>

<script lang="ts">
export default {
  name: 'ChildComponent'
}
</script>

<script setup lang="ts">
import { defineProps, defineEmits } from 'vue'

const props = defineProps<{ message: string }>()
const emit = defineEmits<{
  (e: 'custom-event', payload: string): void
}>()
</script>

<style scoped>
</style>