<script setup lang="ts">
const benefits = [
  {
    icon: '🌱',
    title: 'SOURCED FROM GRASSLAND',
    subtitle: 'REAL FOOD',
    description: 'Our beef jerky is grass fed and grass finished.',
  },
  {
    icon: '💪',
    title: 'HIGH IN PROTEIN, BIG ON TASTE',
    subtitle: 'NUTRITIOUS',
    description: 'Packed with protein, our snacks give you real fuel.',
  },
  {
    icon: '⭐',
    title: 'BY PREMIUM JERKY COMPANY',
    subtitle: 'QUALITY',
    description: 'A tradition like jerky is worth the hard work.',
  },
]
</script>

<template>
  <section class="section-spacing bg-white">
    <div class="container">
      <div class="row g-4 justify-content-center">
        <div v-for="benefit in benefits" :key="benefit.title" class="col-lg-4 col-md-4">
          <div class="benefit-card text-center h-100 p-4">
            <div class="icon-wrapper mb-4">
              <div class="benefit-icon">
                {{ benefit.icon }}
              </div>
            </div>

            <h4 class="fw-bold text-primary-brown mb-2">{{ benefit.title }}</h4>
            <div
              class="subtitle text-uppercase fw-semibold text-muted mb-3"
              style="font-size: 12px; letter-spacing: 1px"
            >
              {{ benefit.subtitle }}
            </div>
            <p class="text-muted">{{ benefit.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.benefit-card {
  transition: transform 0.3s ease;
}

.benefit-card:hover {
  transform: translateY(-5px);
}

.benefit-icon {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, var(--accent-orange), #f39c12);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 32px;
  margin: 0 auto;
  box-shadow: 0 10px 25px rgba(231, 126, 34, 0.3);
}

.icon-wrapper {
  position: relative;
}

.icon-wrapper::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100px;
  height: 100px;
  border: 2px solid rgba(231, 126, 34, 0.2);
  border-radius: 50%;
  z-index: -1;
}
</style>
