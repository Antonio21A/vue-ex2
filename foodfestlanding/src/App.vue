<script>
import HeaderSection from "./components/HeaderSection.vue";
import TicketCard from "./components/TicketCard.vue";
import FooterSection from "./components/FooterSection.vue";
import ticketTiers from "./Data/TicketTiers";

export default {
  components: { HeaderSection, TicketCard, FooterSection },
  data() {
    return { tiers: ticketTiers };
  }
};
</script>

<template>
  <div id="app">
    <HeaderSection />
    <main class="ticket-section">
      <TicketCard v-for="tier in tiers" :key="tier.id" :tier="tier" />
    </main>
    <FooterSection />
  </div>
</template>

<style>
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background-color: #f0f4f8;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.ticket-section {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
  padding: 4rem 0;
}

.ticket-section .card {
  flex: 1 1 250px;
  max-width: 300px;
  box-sizing: border-box;
}

@media (max-width: 768px) {
  .ticket-section {
    gap: 1rem;
  }
  .ticket-section .card {
    flex: 1 1 100%;
    max-width: 100%;
  }
}
</style>
