<template>
  <section class="factual-section">
    <div class="logo-grid">
      <div class="logo-item text-center">
        <img src="../assets/images/proudly_sa.png" alt="Proudly South African" />
        <p>Proudly South African</p>
      </div>
      <div class="logo-item text-center">
        <img src="../assets/images/no_preservatives.svg" alt="No Preservatives" />
        <p>No Preservatives</p>
      </div>
      <div class="logo-item text-center">
        <img src="../assets/images/h_package.svg" alt="Halaal Certified" />
        <p>Hygienically packaged</p>
      </div>
      <div class="logo-item text-center">
        <img src="../assets/images/wholesale.svg" alt="Wholesale" />
        <p>Wholesale distributor</p>
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
  height: 10rem;
  max-width: 120px;
  object-fit: contain;
}

.logo-item p {
  margin-top: 0.5rem;
  font-size: 0.875rem;
  color: #e50102;
  letter-spacing: 1px;
  font-family: 'Cooper Hewitt Bold';
  text-transform: uppercase;
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
