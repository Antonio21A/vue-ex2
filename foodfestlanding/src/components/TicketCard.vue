<script>
export default {
  props: {
    tier: Object
  },
  data() {
    return {
      isFavourite: false
    };
  },
  methods: {
    toggleFavourite() {
      if (this.tier.available) this.isFavourite = !this.isFavourite;
    }
  }
};
</script>

<template>
  <div
    class="card"
    :class="{ featured: tier.featured, unavailable: !tier.available }"
  >
    <div class="card-header">
      <h2>{{ tier.name }}</h2>
      <button class="fav-btn" @click="toggleFavourite" :disabled="!tier.available">
        {{ isFavourite ? "❤️" : "🤍" }}
      </button>
    </div>

    <p class="price" v-if="tier.available">R{{ tier.price }}</p>
    <p class="unavailable-text" v-else>Unavailable 🔒</p>

    <ul>
      <li v-for="(benefit, index) in tier.benefits" :key="index">{{ benefit }}</li>
    </ul>

    <button v-if="tier.available">Select Ticket</button>
  </div>
</template>

<style scoped>
.card {
  background: #ffffff;
  border-radius: 15px;
  padding: 2rem 1.5rem;
  box-shadow: 0 4px 15px rgba(0,0,0,0.08);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transition: 0.3s;
}

.card:not(.unavailable):hover {
  transform: translateY(-5px) scale(1.03);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15);
}

.featured {
  background: linear-gradient(135deg, #002D72, #00A0D1);
  color: white;
}

.featured ul li {
  color: white;
}

.unavailable {
  opacity: 0.5;
  background: #F4F4F4;
  text-align: center;
}

.unavailable-text {
  font-weight: bold;
  color: #777;
  margin: 1rem 0;
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.fav-btn {
  font-size: 1.5rem;
  background: none;
  border: none;
  cursor: pointer;
}

.fav-btn:disabled {
  cursor: not-allowed;
  opacity: 0.4;
}

.price {
  font-size: 1.8rem;
  font-weight: bold;
  color: #002D72;
  margin: 0.5rem 0;
}

ul {
  margin-top: 1rem;
  padding-left: 1rem;
}

li {
  margin-bottom: 0.4rem;
  font-size: 0.95rem;
  color: #444;
}

button {
  margin-top: 1rem;
  padding: 0.6rem 1.2rem;
  border-radius: 50px;
  border: none;
  cursor: pointer;
  background-color: #00A0D1;
  color: white;
  font-weight: bold;
  transition: 0.3s;
}

button:hover {
  background-color: #008bb3;
}
</style>

