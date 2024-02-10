<template>
    <div class="register">
      <h1>Εγγραφή</h1>
      <form @submit.prevent="register">
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" required>
        </div>
        <div>
          <label for="password">Κωδικός:</label>
          <input type="password" id="password" v-model="password" required>
        </div>
        <button type="submit">Εγγραφή</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: "RegisterView",
    data() {
      return {
        email: '',
        password: '',
      };
    },
    methods: {
      register() {
        // Εδώ θα προστεθεί ο κώδικας για την εγγραφή νέων χρηστών
        alert("Λειτουργία εγγραφής δεν έχει υλοποιηθεί ακόμη.");
      }
    }
  };
  </script>
  
  <style scoped>
  .register {
    max-width: 400px;
    margin: 50px auto;
    text-align: center;
  }
  </style>
  