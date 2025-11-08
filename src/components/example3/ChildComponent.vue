<!-- ChildComponent.vue -->
<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ id }}</p>
    <p>{{ password }}</p> 
    <button @click="$emit('custom-event', 'Hello from child')">Send Event</button>
  </div>
</template>

<script>
export default {
  props: ['message','id','password'],
};
</script>
