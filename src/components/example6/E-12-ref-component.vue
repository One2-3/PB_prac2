<template>
  <div>
    <input ref="inputField" type="text" placeholder="Click the button to focus" />
    <button @click="focusInput">Focus Input</button>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
  name: 'E12RefComponent',
  setup() {
    const inputField = ref(null); // DOM 요소에 대한 ref 선언

    const focusInput = () => {
      inputField.value.focus(); // ref를 통해 DOM 요소에 접근
    };

    onMounted(() => {
      console.log(inputField); // 컴포넌트가 마운트된 후, inputField에 접근 가능
      if(inputField.value) {
        inputField.value.focus();
      }
    });


    return {
      inputField,
      focusInput
    };
  }
};
</script>
