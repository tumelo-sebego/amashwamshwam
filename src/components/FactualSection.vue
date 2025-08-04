<template>
  <section class="factual-section">
    <div class="logo-grid">
      <div class="logo-item">
        <img src="../assets/images/proudly_sa.png" alt="Proudly South African" />
      </div>
      <div class="logo-item">
        <img src="../assets/images/no_preservatives.svg" alt="No Preservatives" />
      </div>
      <div class="logo-item">
        <img src="../assets/images/h_package.svg" alt="Halaal Certified" />
      </div>
      <div class="logo-item">
        <img src="../assets/images/wholesale.svg" alt="Wholesale" />
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// No script needed for this component
</script>

<style scoped>
.factual-section {
  padding: 2rem 1rem;
  background-color: #f8f8f8;
}

.logo-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem;
  align-items: center;
  justify-items: center;
  max-width: 1200px;
  margin: 0 auto;
}

.logo-item img {
  height: 60px;
  max-width: 120px;
  object-fit: contain;
}

@media (max-width: 768px) {
  .factual-section {
    padding: 2rem 0;
  }
  .logo-grid {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    -webkit-overflow-scrolling: touch;
    gap: 0;
    padding: 0 1rem;
  }

  .logo-grid::-webkit-scrollbar {
    display: none;
  }

  .logo-item {
    flex: 0 0 55%;
    scroll-snap-align: start;
    text-align: center;
    margin-right: -2rem;
  }
}
</style>
