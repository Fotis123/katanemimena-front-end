<template>
    <div class="home">
      <h1>Καλωσήρθατε στο Εθνικό Μητρώο Αιμοδοτών</h1>
      <p>Η πλατφόρμα όπου οι πολίτες κάνουν τη διαφορά.</p>
      <router-link to="/login">Σύνδεση</router-link>
    </div>
  </template>
  
  <script>
  export default {
    name: "HomeView",
  };
  </script>
  
  <style scoped>
  .home {
    text-align: center;
    margin-top: 50px;
  }
  </style>
  