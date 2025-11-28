<template>
  <header class="header">
    <div class="overlay">
      <h1>Cape Town Food Fest 2025</h1>
      <p>Celebrate food, music, and community! Choose your perfect ticket below.</p>
      <button class="cta-btn">Notify Me</button>
    </div>
  </header>
</template>

<style scoped>
.header {
  width: 100%;
  background: url('https://i.postimg.cc/pXS0DjtX/food-ticket-2.avif') center/cover no-repeat;
  height: 60vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.overlay {
  text-align: center;
  background-color: rgba(0, 45, 114, 0.7);
  padding: 2rem;
  border-radius: 20px;
  color: white;
}

.header h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  font-weight: 800;
}

.header p {
  font-size: 1.3rem;
  margin-bottom: 1.5rem;
}

.cta-btn {
  background-color: #00A0D1;
  color: white;
  padding: 0.8rem 1.5rem;
  border: none;
  border-radius: 50px;
  font-size: 1.1rem;
  cursor: pointer;
  transition: 0.3s;
}

.cta-btn:hover {
  background-color: #008bb3;
}
</style>
