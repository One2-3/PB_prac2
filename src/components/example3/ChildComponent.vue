<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ id }}</p>
    <p>{{ password }}</p>
    <button @click="sendEvent">Send Event</button>
  </div>
</template>

<script lang="ts">
export default {
  name: 'ChildComponent'
}
</script>

<script setup lang="ts">
const { message, id, password } = defineProps<{
  message: string
  id: string | number
  password: string | number
}>()

const emit = defineEmits<{
  (e: 'custom-event', payload: string): void
}>()

const sendEvent = () => {
  emit('custom-event', 'Hello from child')
}
</script>
