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
export default {
  name: 'E07OptionsApi',

  props: {
    title: {
      type: String,
      default: 'User Information',
      required: false
    }
  },

  data() {
    return {
      firstName: 'John',
      lastName: 'Doe',
      greetCount: 0,
      message: ''
    };
  },

  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    }
  },

  methods: {
    greet() {
      this.greetCount++;
      this.message = `Hello, ${this.fullName}!`;
    },
    resetGreetCount() {
      this.greetCount = 0;
    }
  },

  watch: {
    greetCount(newValue, oldValue) {
      console.log(`Greet count changed from ${oldValue} to ${newValue}`);
      if (newValue >= 3) {
        this.message = "That's enough greetings for now!";
      }
    }
  },

  beforeCreate() {
    console.log('beforeCreate hook');
  },

  created() {
    console.log('created hook');
  },

  beforeMount() {
    console.log('beforeMount hook');
  },

  mounted() {
    console.log('mounted hook');
  },

  beforeUpdate() {
    console.log('beforeUpdate hook');
  },

  updated() {
    console.log('updated hook');
  },

  beforeUnmount() {
    console.log('beforeUnmount hook');
  },

  unmounted() {
    console.log('unmounted hook');
  }
};
</script>
