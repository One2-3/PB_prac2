<template>
  <h3>Child 1</h3>
  <div>
    <p>{{ sharedMessage }}</p>
  </div>

  <h3>Child 2</h3>
  <div>
    <ChildComponent2 />
  </div>
</template>

<script lang="ts">
export default {
  name: 'ChildComponent1'
}
</script>

<script setup lang="ts">
import { inject } from 'vue'
import ChildComponent2 from '@/components/example4/ChildComponent2.vue'

const sharedMessage = inject<string>('sharedMessage', '')
</script>

<style scoped>
p {
  color: red;
}
</style>
