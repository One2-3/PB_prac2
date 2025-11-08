<template>
  <div>Hello, {{ message }}</div>
</template>

<script>
export default {
  name: "E01Instance",
  data() {
    const name ="JiYu"
    return {
      message: name
    };
  }
};
</script>

<style scoped>
div {
  color: blue;
  font-size: 20px;
  font-weight: bold;
}
</style>
