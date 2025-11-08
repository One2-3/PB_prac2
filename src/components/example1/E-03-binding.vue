<template>
  <div>
    <input v-model="id" />
    <input v-model="password" />
    <p>{{ message }}</p>
    <button @click="whoami">whoami</button>
  </div>
</template>

<script lang="ts">
export default {
  name: 'E03Binding'
}
</script>

<script setup lang="ts">
import { ref } from 'vue'

const message = ref('Hello Vue')
const id = ref('')
const password = ref('')

const whoami = () => {
  message.value = `${id.value} ${password.value}`
}
</script>
