<!-- ParentComponent.vue -->
<template>
  <div>
    <ChildComponent
        :message="parentMessage"
        :id ="1"
        :password ="1234"
        @custom-event="handleEvent"
    />
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  name: "E05ParentComponent",
  data() {
    return {
      parentMessage: 'Hello from parent'
    };
  },
  methods: {
    handleEvent(payload) {
      console.log(payload);
    }
  },
  components: {
    ChildComponent
  }
};
</script>
