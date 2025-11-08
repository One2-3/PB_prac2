<template>
  <div>
    <h2>{{ title }}</h2>
    <p>Full Name: {{ fullName }}</p>
    <input v-model="firstName" placeholder="First Name" />
    <input v-model="lastName" placeholder="Last Name" />
    <button @click="greet">Greet</button>
    <p>Greeting Count: {{ greetCount }}</p>
    <p>{{ message }}</p>
  </div>
</template>

<script>
import { ref, computed, watch, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue';

export default {
  name: 'E08CompositionApi',

  props: {
    title: {
      type: String,
      default: 'User Information'
    }
  },

  setup(props) {
    // 반응형 상태 정의
    const firstName = ref('John');
    const lastName = ref('Doe');
    const greetCount = ref(0);
    const message = ref('');

    // 계산된 속성
    const fullName = computed(() => `${firstName.value} ${lastName.value}`);

    // 메서드 정의
    const greet = () => {
      greetCount.value++;
      message.value = `Hello, ${fullName.value}!`;
    };

    const resetGreetCount = () => {
      greetCount.value = 0;
    };

    // 감시자(watch) 설정
    watch(greetCount, (newValue, oldValue) => {
      console.log(`Greet count changed from ${oldValue} to ${newValue}`);
      if (newValue >= 3) {
        message.value = "That's enough greetings for now!";
      }
    });

    // 라이프사이클 훅 정의
    onBeforeMount(() => {
      console.log('beforeMount hook');
    });

    onMounted(() => {
      console.log('mounted hook');
    });

    onBeforeUpdate(() => {
      console.log('beforeUpdate hook');
    });

    onUpdated(() => {
      console.log('updated hook');
    });

    onBeforeUnmount(() => {
      console.log('beforeUnmount hook');
    });

    onUnmounted(() => {
      console.log('unmounted hook');
    });

    return {
      firstName,
      lastName,
      greetCount,
      message,
      fullName,
      greet,
      resetGreetCount,
    };
  }
};
</script>
