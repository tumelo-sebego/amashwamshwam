<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import chillyHeadBg from '../assets/images/chilly_head_bg.png'
import chillySnack from '../assets/images/chlly-snack.png'
import cheeseHeadBg from '../assets/images/cheese_head_bg.png'
import cheeseSnack from '../assets/images/cheese-snack.png'

const currentSlide = ref(0)
let intervalId: ReturnType<typeof setInterval> | null = null

const slides = [
  {
    title: 'SAVOUR THE CHILLY ZING!',
    subtitle: 'A fiery kick of flavour in every bite, made for the bold and adventurous.',
    image: chillyHeadBg,
    productImage: chillySnack,
  },
  {
    title: 'INDULGE IN CHEESY PERFECTION!',
    subtitle: 'A rich and creamy taste that melts in your mouth, a true delight for cheese lovers.',
    image: cheeseHeadBg,
    productImage: cheeseSnack,
  },
]

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

onMounted(() => {
  intervalId = setInterval(nextSlide, 5000) // Move every 5 seconds
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
                <div style="position: relative; z-index: 20;">
                  <h1 class="display-3 fw-bold mb-4 text-shadow">{{ slide.title }}</h1>
                  <p class="fs-5 mb-4 text-shadow">{{ slide.subtitle }}</p>
                </div>

                <img
                  :src="slide.productImage"
                  class="product-image"
                  alt="Product Image"
                  style="
                    position: absolute;
                    bottom: -30px;
                    right: 23rem;
                    width: 390px;
                    height: auto;
                    z-index: 10;
                    transform: rotate(-14deg);
                  "
                />

                <div style="position: relative; z-index: 20;">
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
  width: calc(100% * 2); /* 2 slides */
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
