<!-- ChildComponent.vue -->
<template>
  <h3> Child 1 </h3>
  <div>
    <p>{{ sharedMessage }}</p>
  </div>

  <h3> Child 2 </h3>
  <div>
    <ChildComponent2 />
  </div>
</template>

<script>
import ChildComponent2 from "@/components/example4/ChildComponent2.vue";

export default {
  components: {ChildComponent2},
  inject: ['sharedMessage']
};
</script>


<style scoped>
p {
  color: red;
}
</style>
