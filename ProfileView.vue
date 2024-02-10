<template>
    <div class="profile">
      <h1>Προφίλ Χρήστη</h1>
      <form @submit.prevent="updateProfile">
        <div>
          <label for="name">Όνομα:</label>
          <input type="text" id="name" v-model="name" required>
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" disabled>
        </div>
        <!-- Προσθέστε εδώ άλλα πεδία ανάλογα με τις απαιτήσεις της εφαρμογής -->
        <button type="submit">Ενημέρωση Προφίλ</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: "ProfileView",
    data() {
      return {
        name: '',
        email: '',
        // Προσθέτουμε εδώ άλλες μεταβλητές ανάλογα με τις απαιτήσεις του προφίλ
      };
    },
    methods: {
      updateProfile() {
        // Εδώ θα προστεθεί ο κώδικας για την ενημέρωση του προφίλ
        alert("Λειτουργία ενημέρωσης προφίλ δεν έχει υλοποιηθεί ακόμη.");
      }
    }
  };
  </script>
  
  <style scoped>
  .profile {
    max-width: 400px;
    margin: 50px auto;
    text-align: center;
  }
  </style>
  