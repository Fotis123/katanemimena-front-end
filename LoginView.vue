<template>
    <div class="login">
      <h1>Σύνδεση</h1>
      <form @submit.prevent="login">
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" required>
        </div>
        <div>
          <label for="password">Κωδικός:</label>
          <input type="password" id="password" v-model="password" required>
        </div>
        <button type="submit">Σύνδεση</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: "LoginView",
    data() {
      return {
        email: '',
        password: '',
      };
    },
    methods: {
      login() {
        // Εδώ θα προστεθεί ο κώδικας για την αυθεντικοποίηση
        alert("Λειτουργία σύνδεσης δεν έχει υλοποιηθεί ακόμη.");
      }
    }
  };
  </script>
  
  <style scoped>
  .login {
    max-width: 400px;
    margin: 50px auto;
    text-align: center;
  }
  </style>
  