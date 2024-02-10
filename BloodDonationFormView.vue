<template>
    <div class="donation-form">
      <h1>Αίτηση για Αιμοδοσία</h1>
      <form @submit.prevent="submitDonationForm">
        <div>
          <label for="fullName">Ονοματεπώνυμο:</label>
          <input type="text" id="fullName" v-model="fullName" required>
        </div>
        <div>
          <label for="bloodType">Ομάδα Αίματος:</label>
          <select id="bloodType" v-model="bloodType" required>
            <option value="">Επιλέξτε...</option>
            <option value="A+">A+</option>
            <option value="A-">A-</option>
            <option value="B+">B+</option>
            <option value="B-">B-</option>
            <option value="AB+">AB+</option>
            <option value="AB-">AB-</option>
            <option value="O+">O+</option>
            <option value="O-">O-</option>
          </select>
        </div>
        <div>
          <label for="dateOfBirth">Ημερομηνία Γέννησης:</label>
          <input type="date" id="dateOfBirth" v-model="dateOfBirth" required>
        </div>
        <div>
          <label for="residence">Τόπος Διαμονής:</label>
          <input type="text" id="residence" v-model="residence" required>
        </div>
        <div>
          <label for="lastDonation">Ημερομηνία Τελευταίας Αιμοδοσίας (εάν υπάρχει):</label>
          <input type="date" id="lastDonation" v-model="lastDonation">
        </div>
        <button type="submit">Υποβολή Αίτησης</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: "BloodDonationFormView",
    data() {
      return {
        fullName: '',
        bloodType: '',
        dateOfBirth: '',
        residence: '',
        lastDonation: '',
      };
    },
    methods: {
      async submitDonationForm() {
        const citizen = {
          fullName: this.fullName,
          bloodType: this.bloodType,
          dateOfBirth: this.dateOfBirth,
          residence: this.residence,
          lastDonation: this.lastDonation,
        };
        await this.registerBloodDonor(citizen);
      },
      async registerBloodDonor(citizen) {
        try {
          const response = await fetch('/api/blood-donation/citizens', {
            method: 'POST',
            headers: {
              'Content-Type': 'application/json',
            },
            body: JSON.stringify(citizen),
          });
  
          if (!response.ok) throw new Error('Network response was not ok.');
  
          alert('Η αίτηση υποβλήθηκε επιτυχώς.');
          // Καθαρίστε τη φόρμα ή κάντε redirect
        } catch (error) {
          console.error('Σφάλμα κατά την υποβολή της αίτησης:', error);
          alert('Υπήρξε σφάλμα κατά την υποβολή της αίτησης.');
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .donation-form {
    max-width: 400px;
    margin: 50px auto;
    text-align: center;
  }
  </style>
  