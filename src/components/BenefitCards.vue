<script setup lang="ts">
import SmileyFace from './icons/SmileyFace.vue'

const benefits = [
  {
    icon: 'smiley_face2',
    title: 'SOURCED FROM GRASSLAND',
    subtitle: 'REAL FOOD',
    description: 'Our beef jerky is grass fed and grass finished.',
  },
  {
    icon: 'smiley_face1',
    title: 'HIGH IN PROTEIN, BIG ON TASTE',
    subtitle: 'NUTRITIOUS',
    description: 'Packed with protein, our snacks give you real fuel.',
  },
  {
    icon: 'smiley_face3',
    title: 'BY PREMIUM JERKY COMPANY',
    subtitle: 'QUALITY',
    description: 'A tradition like jerky is worth the hard work.',
  },
]
</script>

<template>
  <section class="section-spacing bg-white">
    <div class="container">
      <div class="benefit-scroll-wrapper">
        <div class="row g-4 flex-nowrap flex-md-wrap justify-content-md-center">
          <div v-for="benefit in benefits" :key="benefit.title" class="col-10 col-md-4 col-lg-4">
            <div class="benefit-card text-center h-100 p-4">
              <div class="icon-wrapper mb-4">
                <div class="benefit-icon">
                  <SmileyFace
                    :iconName="benefit.icon"
                    outlineColor="var(--cream)"
                    faceColor="#E50102"
                  />
                </div>
              </div>

              <h4 class="fw-bold mb-2">{{ benefit.title }}</h4>
              <div
                class="subtitle text-uppercase fw-semibold mb-3"
                style="font-size: 12px; letter-spacing: 1px"
              >
                {{ benefit.subtitle }}
              </div>
              <p class="">{{ benefit.description }}</p>
            </div>
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

.benefit-card h4 {
  font-family: 'Cooper Hewitt Bold', sans-serif;
  color: #e50102;
}

.benefit-card p,
.benefit-card .subtitle {
  font-family: 'Cooper Hewitt', sans-serif;
  color: #e50102;
}

.benefit-icon {
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
}

.icon-wrapper {
  position: relative;
}

@media (max-width: 767.98px) {
  .benefit-scroll-wrapper {
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    scrollbar-width: none; /* Firefox */
  }

  .benefit-scroll-wrapper::-webkit-scrollbar {
    display: none; /* Chrome, Safari, Opera */
  }

  .benefit-scroll-wrapper .row {
    padding-left: 1rem;
    padding-right: 1rem;
    margin-left: 0;
    margin-right: 0;
  }
}
</style>
