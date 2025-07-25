<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const currentSlide = ref(0)
let intervalId: ReturnType<typeof setInterval> | null = null

const slides = [
  {
    title: "HIGH PROTEIN SNACK YOU'VE EVER TASTED!",
    subtitle: 'Enjoy the taste of victory meat jerky that comes with a friend in your pocket',
    image: 'https://images.pexels.com/photos/422220/pexels-photo-422220.jpeg?w=800&h=600&fit=crop',
    features: ['GRASS FED', 'HIGH PROTEIN', 'LOW FAT'],
  },
  {
    title: 'PREMIUM QUALITY JERKY FOR REAL TASTE!',
    subtitle: 'Made from the finest cuts of grass-fed beef with no artificial preservatives',
    image:
      'https://images.pexels.com/photos/1128678/pexels-photo-1128678.jpeg?w=800&h=600&fit=crop',
    features: ['ALL NATURAL', 'NO MSG', 'GLUTEN FREE'],
  },
  {
    title: 'ADVENTURE AWAITS WITH EVERY BITE!',
    subtitle: 'Fuel your adventures with our high-protein, low-fat jerky snacks',
    image:
      'https://images.pexels.com/photos/1128431/pexels-photo-1128431.jpeg?w=800&h=600&fit=crop',
    features: ['PORTABLE', 'LONG LASTING', 'NUTRITIOUS'],
  },
]

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

onMounted(() => {
  intervalId = setInterval(nextSlide, 5000) // Move every 0.5 seconds as requested
})

onUnmounted(() => {
  if (intervalId) {
    clearInterval(intervalId)
  }
})
</script>

<template>
  <section class="hero-section d-flex align-items-center justify-content-center">
    <div
      class="carousel-container position-relative overflow-hidden"
      style="border-radius: 25px; height: 600px; width: 100%"
    >
      <transition-group name="fade" tag="div" class="h-100">
        <div
          v-for="(slide, index) in slides"
          :key="index"
          v-show="currentSlide === index"
          class="carousel-slide w-100 h-100 position-absolute"
        >
          <div
            class="slide-bg h-100"
            :style="{
              backgroundImage: `url(${slide.image})`,
              backgroundSize: 'cover',
              backgroundPosition: 'center',
              backgroundRepeat: 'no-repeat',
            }"
          >
            <div class="overlay"></div>
          </div>

          <div
            class="container position-absolute top-50 start-50 translate-middle text-white text-left"
          >
            <div class="row justify-content-start">
              <div class="col-lg-8">
                <h1 class="display-3 fw-bold mb-4 text-shadow">{{ slide.title }}</h1>
                <p class="fs-5 mb-4 text-shadow">{{ slide.subtitle }}</p>

                <div class="d-flex justify-content-start flex-wrap gap-3 mb-4">
                  <span
                    v-for="feature in slide.features"
                    :key="feature"
                    class="badge bg-primary fs-6 px-3 py-2 rounded-pill"
                  >
                    {{ feature }}
                  </span>
                </div>

                <button class="btn btn-primary btn-lg px-5 py-3">ORDER NOW →</button>

                <div class="mt-4">
                  <div
                    class="quality-badge bg-white text-primary-brown rounded-circle d-inline-flex align-items-center justify-content-center"
                    style="width: 80px; height: 80px"
                  >
                    <div class="text-center">
                      <div class="fw-bold" style="font-size: 12px">QUALITY</div>
                      <div class="fw-bold" style="font-size: 12px">FIRST</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </transition-group>
    </div>

    <!-- Slide indicators -->
    <div class="position-absolute bottom-0 start-50 translate-middle-x mb-4">
      <div class="d-flex gap-2">
        <button
          v-for="(slide, index) in slides"
          :key="index"
          class="carousel-indicator"
          :class="{ active: currentSlide === index }"
          @click="currentSlide = index"
        ></button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  background: var(--cream);
  padding: 1rem 6rem;
}

.carousel-track {
  width: calc(100% * 3); /* 3 slides */
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.text-shadow {
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
}

.quality-badge {
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.carousel-indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: 2px solid white;
  background: transparent;
  transition: all 0.3s ease;
}

.carousel-indicator.active {
  background: white;
}

.carousel-indicator:hover {
  background: rgba(255, 255, 255, 0.7);
}

.transition-transform {
  transition: transform 0.8s ease-in-out;
}

/* Medium devices (tablets, 768px and up) */
@media (max-width: 768px) {
  /* Styles for medium devices and up */
  .hero-section {
    padding: 1rem 3rem;
  }
}

@media (max-width: 576px) {
  /* Styles for small devices and up */
  .hero-section {
    padding: 2rem 1rem !important;
  }
}
</style>
