<template>
  <div id="app">
    <header>
      <h1>Cape Town Food Fest 🎉</h1>
      <p>Join us for a weekend of food, fun, and community!</p>

      <!-- Controls -->
      <div class="controls">
        <button @click="sortByPrice">Sort by Price</button>
        <button @click="filterFeatured">Show Featured Only</button>
        <button @click="resetFilter">Reset</button>
        <button @click="toggleTheme">
          Toggle {{darkMode ? 'Light' : 'Dark'}} Mode
        </button>
      </div>
    </header>

    <!-- Ticket Cards -->
    <section class="tickets">
      <TicketCard
        v-for="(ticket, index) in Tickets"
        :key="index"
        :name="ticket.name"
        :price="ticket.price"
        :benefits="ticket.benefits"
        :featured="ticket.featured"
      />
    </section>
  </div>
</template>

<script>
import tickets from "./data/tickets";
import TicketCard from "./components/TicketCard.vue";

export default {
  components: { TicketCard },
  data() {
    return { 
      tickets,
      Tickets: tickets, 
      darkMode: false
    };
  },
  methods: {
    sortByPrice() {
      this.displayTickets = [...this.Tickets].sort(
        (a, b) =>
        parseInt(a.price.replace("R", "")) -
        parseInt(b.price.replace("R", ""))
      );
    },
    filterFeatured() {
      this.Tickets = this.tickets.filter(t => t.featured);
    },
    resetFilter() {
      this.Tickets = this.tickets;
    },
    toggleTheme() {
      this.darkMode = !this.darkMode;
      document.body.classList.toggle("dark", this.darkMode);
    }
  }
};
</script>

<style>
header {
  text-align: center;
  margin-bottom: 2rem;
}
.controls {
  margin: 1rem 0;
}
.controls button {
  margin: 0.3rem;
  padding: 0.5rem 1rem;
  border: none;
  background: #2196f3;
  color: white;
  border-radius: 6px;
  cursor: pointer;
}
.controls button:hover {
  background: #1976d2;
}
.tickets {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
}
.body.dark {
  background: #121212;
  color: #c00c0c;
}
.body.dark .ticket-card {
  background: #1e1e1e;
  border-color: #e0e0e0;
}
.dark .ticket-card li {
  color: #ffeb3b;
}
</style>