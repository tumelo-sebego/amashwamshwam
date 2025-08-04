<script setup lang="ts">
import SmileyFace from './icons/SmileyFace.vue'

const benefits = [
  {
    icon: 'smiley_face2',
    title: 'Local Roots',
    subtitle: 'REAL FOOD',
    description:
      'AmaShwamShwam is more than just a snack, it’s a township tradition reborn. Our name, packaging, and flavour pay tribute to South African childhood memories. Proudly made for the people, by the people.',
  },
  {
    icon: 'smiley_face3',
    title: 'Built for Hustlers',
    subtitle: 'NUTRITIOUS',
    description:
      'From schoolyards to street corners, AmaShwamShwam empowers youth to earn. Our reseller packs make it easy to start a side hustle with just R175. No limits, just profit, passion, and local hustle.',
  },
  {
    icon: 'smiley_face1',
    title: 'Big Flavour',
    subtitle: 'QUALITY',
    description:
      'Founded by Lesedi & Tsholofelo, two bold young dreamers. Their goal? Use flavour to build a movement. AmaShwamShwam is proof that youth leads change.',
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
                  <SmileyFace :iconName="benefit.icon" outlineColor="#ffc801" faceColor="#E50102" />
                </div>
              </div>

              <h4 class="fw-bold mb-2">{{ benefit.title }}</h4>

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
  text-align: justify;
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
