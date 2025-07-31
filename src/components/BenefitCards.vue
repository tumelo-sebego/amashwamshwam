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
  <section class="section-spacing bg-cream">
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

      <div class="text-center mt-5">
        <button class="btn-custom"><span>FIND OUT MORE</span></button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.benefit-card {
  transition: transform 0.3s ease;
}

.benefit-card:hover {
  /* transform: translateY(-5px); */
}

.benefit-icon {
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
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

.icon-wrapper {
  position: relative;
}

.btn-custom {
  position: relative;
  border: none;
  font-size: 1rem;
  font-family: 'DK Frozen Memory';
  background: none;
  padding: 10px 20px;
  font-weight: bold;
  cursor: pointer;
  color: #e50102;
  border-radius: 13px;
  padding: 12px;
}

.btn-custom span {
  position: relative;
  z-index: 2;
  letter-spacing: 2px;
  font-size: 20px;
}

.btn-custom::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #ffc801;
  /* border: inherit; */
  border: 4px solid #e50102;
  z-index: 1;
  border-radius: inherit;
}

.btn-custom::after {
  content: '';
  position: absolute;
  top: 8px;
  left: -8px;
  width: 100%;
  height: 100%;
  background-color: #fde26f;
  border: 4px solid #e50102;
  z-index: 0;
  border-radius: inherit;
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
