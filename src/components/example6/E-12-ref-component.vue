<template>
  <div>
    <input
      ref="inputField"
      type="text"
      placeholder="Click the button to focus"
    />
    <button @click="focusInput">Focus Input</button>
  </div>
</template>

<script lang="ts">
export default {
  name: 'E12RefComponent'
}
</script>

<script setup lang="ts">
import { ref, onMounted } from 'vue'

const inputField = ref<HTMLInputElement | null>(null)

const focusInput = () => {
  if (inputField.value) {
    inputField.value.focus()
  }
}

onMounted(() => {
  console.log(inputField)
  if (inputField.value) {
    inputField.value.focus()
  }
})
</script>
