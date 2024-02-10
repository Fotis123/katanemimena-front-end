<template>
    <div>
      <h1>Λίστα Πολιτών</h1>
      <ul>
        <li v-for="citizen in citizens" :key="citizen.id">{{ citizen.name }}</li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        citizens: [],
      };
    },
    mounted() {
      this.fetchCitizens();
    },
    methods: {
      async fetchCitizens() {
        try {
          const response = await fetch('http://localhost:8080/api/blood-donation/citizens');
          if (!response.ok) throw new Error('Network response was not ok');
          this.citizens = await response.json();
        } catch (error) {
          console.error('Σφάλμα κατά τη λήψη των πολιτών:', error);
        }
      }
    }
  };
  </script>
  