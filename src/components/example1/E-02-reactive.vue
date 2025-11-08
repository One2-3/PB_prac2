<template>
  <div>{{ fullName }}</div>
</template>

<script lang="ts">
export default {
  name: 'E02Reactive'
}
</script>

<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'

const firstName = ref('Kyungsu')
const lastName = ref('Lee')

const fullName = computed(() => `${firstName.value} ${lastName.value}`)

onMounted(() => {
  console.log('mounted')

  let a = 10

  setTimeout(() => {
    console.log('setTimeout')
    a = 20
    console.log(a)
  }, 500)

  setTimeout(() => {
    lastName.value = '123'
  }, 1000)

  setTimeout(() => {
    firstName.value = 'KSL'
  }, 2000)
})
</script>
