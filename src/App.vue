<template>
  <E06ParentComponent/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import E06ParentComponent from "@/components/example4/ParentComponent.vue";

export default defineComponent({
  name: 'App',
  components: {
    E06ParentComponent
  }
});
</script>

<style>
</style>
