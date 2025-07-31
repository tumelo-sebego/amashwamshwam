<script setup lang="ts">
import { ref } from 'vue'
import social1 from '../assets/images/social1.jpg'
import social2 from '../assets/images/social2.jpg'
import social3 from '../assets/images/social3.jpg'
import social4 from '../assets/images/social4.jpg'
import social5 from '../assets/images/social5.jpg'
import social6 from '../assets/images/social6.jpg'
import social7 from '../assets/images/social7.jpg'
import socialBg from '../assets/images/socials_bg.png'
import IconChevronLeft from './icons/IconChevronLeft.vue'
import IconChevronRight from './icons/IconChevronRight.vue'

const socialImages = [
  { image: social1 },
  { image: social2 },
  { image: social3 },
  { image: social4 },
  { image: social5 },
  { image: social6 },
  { image: social7 },
]

const scrollWrapper = ref<HTMLElement | null>(null)

const scrollLeft = () => {
  if (scrollWrapper.value) {
    scrollWrapper.value.scrollBy({ left: -200, behavior: 'smooth' })
  }
}

const scrollRight = () => {
  if (scrollWrapper.value) {
    scrollWrapper.value.scrollBy({ left: 200, behavior: 'smooth' })
  }
}
</script>

<template>
  <section class="section-spacing bg-cream">
    <div class="container">
      <div class="social-container py-5" :style="{ backgroundImage: `url(${socialBg})` }">
        <div class="row mb-5">
          <div class="col-12 text-center">
            <h2 class="display-4 mb-3 title">OUR SOCIALS</h2>
          </div>
        </div>

        <div class="social-scroll-wrapper" ref="scrollWrapper">
          <div class="row gx-4 flex-nowrap">
            <div v-for="(social, index) in socialImages" :key="index" class="col-10 col-md-3">
              <div class="social-card rounded-4 overflow-hidden shadow-lg">
                <div class="social-image-container">
                  <img :src="social.image" alt="Social Image" class="img-fluid" />
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="d-flex justify-content-center mt-4">
          <button class="btn-white-round me-2" @click="scrollLeft">
            <IconChevronLeft />
          </button>
          <button class="btn-white-round" @click="scrollRight">
            <IconChevronRight />
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.social-container {
  background-image: url('../assets/images/social_bg.png');
  background-size: cover;
  background-position: center;
  border-radius: 25px;
}

.social-card {
  height: 300px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background-color: white;
}

.title {
  color: #f8f8f8;
}

.social-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2) !important;
}

.social-image-container {
  height: 100%;
  overflow: hidden;
}

.social-image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.social-scroll-wrapper {
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  scrollbar-width: none; /* Firefox */
}

.social-scroll-wrapper::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Opera */
}

.social-scroll-wrapper .row {
  padding-left: 1rem;
  padding-right: 1rem;
  margin-left: 0;
  margin-right: 0;
}

.btn-white-round {
  background-color: white;
  border: 1px solid #ccc;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  cursor: pointer;
}
</style>
