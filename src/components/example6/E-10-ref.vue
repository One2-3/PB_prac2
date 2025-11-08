<template>
  <div>
    <p>Count: {{ count }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'E10Ref',
  setup() {
    const count = ref(0); // ref로 원시 값 생성

    const increment = () => {
      count.value++; // ref는 .value를 통해 값을 접근
    };

    return {
      count,
      increment
    };
  }
};
</script>
