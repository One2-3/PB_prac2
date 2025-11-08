<!-- ParentComponent.vue -->
<template>
  <div>
    <ChildComponent1 />
  </div>
</template>

<script>

import ChildComponent1 from "@/components/example4/ChildComponent1.vue";

export default {
  name: "E06ParentComponent",
  provide() {
    return {
      sharedMessage: 'Hello from provide'
    };
  },
  components: {
    ChildComponent1
  }
};
</script>
