<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import cheeseHero from '../assets/images/cheese_hero.jpg'
import chillyHero from '../assets/images/chilli_hero.jpg'
import cheeseHeroMobile from '../assets/images/cheese_hero_mobile.jpg'
import chilliHeroMobile from '../assets/images/chilli_hero_mobile.jpg'

const currentSlide = ref(0)
let intervalId: ReturnType<typeof setInterval> | null = null

const slides = [
  {
    desktop: chillyHero,
    mobile: chilliHeroMobile,
  },
  {
    desktop: cheeseHero,
    mobile: cheeseHeroMobile,
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
  <section class="hero-section">
    <div class="carousel-container">
      <transition-group name="fade" tag="div" class="h-100">
        <div
          v-for="(slide, index) in slides"
          :key="index"
          v-show="currentSlide === index"
          class="carousel-slide"
        >
          <picture>
            <source :srcset="slide.mobile" media="(max-width: 768px)" />
            <source :srcset="slide.desktop" media="(min-width: 769px)" />
            <img :src="slide.desktop" alt="Hero Image" class="hero-image" />
          </picture>
        </div>
      </transition-group>
    </div>
    <!-- Slide indicators -->
    <div class="carousel-indicators">
      <button
        v-for="(slide, index) in slides"
        :key="index"
        class="carousel-indicator"
        :class="{ active: currentSlide === index }"
        @click="currentSlide = index"
      ></button>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  position: relative;
  width: 100%;
  height: 600px; /* Or adjust as needed */
  background: var(--cream);
  padding: 1rem 6rem;
}

.carousel-container {
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 25px;
  position: relative;
}

.carousel-slide {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
}

.hero-image {
  width: 100%;
  height: 100%;
  object-fit: cover; /* This will make the image fill the container */
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.carousel-indicators {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 10px;
  z-index: 10;
}

.carousel-indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: 2px solid white;
  background: transparent;
  transition: all 0.3s ease;
  cursor: pointer;
}

.carousel-indicator.active {
  background: white;
}

@media (max-width: 768px) {
  .hero-section {
    padding: 1rem 3rem;
    height: 400px;
  }
}

@media (max-width: 576px) {
  .hero-section {
    padding: 2rem 1rem !important;
    height: 33rem;
  }
}
</style>
