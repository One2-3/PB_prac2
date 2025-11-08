<template>
  <div>
    <ChildComponent
      :message="parentMessage"
      :id="1"
      :password="1234"
      @custom-event="handleEvent"
    />
  </div>
</template>

<script lang="ts">
export default {
  name: 'E05ParentComponent'
}
</script>

<script setup lang="ts">
import { ref } from 'vue'
import ChildComponent from './ChildComponent.vue'

const parentMessage = ref('Hello from parent')

const handleEvent = (payload: string) => {
  console.log(payload)
}
</script>
