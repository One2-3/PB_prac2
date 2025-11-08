<template>
  <div>
    <input v-model="id" />
    <input v-model="password" />
    <p>{{ message }}</p>
    <button @click="() => {
      this.message = this.id + ' ' + this.password;
    }">whoami</button>
  </div>
</template>

<script>
export default {
  name: "E03Binding",
  data() {
    return {
      message: "Hello Vue",
      id: "",
      password: "" 
    };
  }
};
</script>
