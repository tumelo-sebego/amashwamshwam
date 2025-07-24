<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-light py-3">
    <div class="container">
      <a class="navbar-brand" href="#">
        <img
          src="https://images.pexels.com/photos/128867/coins-currency-investment-insurance-128867.jpeg?w=50&h=50&fit=crop"
          alt="Wild Jerky"
          height="40"
          class="d-inline-block align-text-top me-2"
        />
        <span class="fw-bold text-primary-brown fs-4">WILD JERKY</span>
      </a>

      <button class="navbar-toggler" type="button" @click="toggleMenu">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" :class="{ show: isMenuOpen }">
        <ul class="navbar-nav mx-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link fw-semibold text-uppercase" href="#">Shop Jerky</a>
          </li>
          <li class="nav-item">
            <a class="nav-link fw-semibold text-uppercase" href="#">Recipes</a>
          </li>
          <li class="nav-item">
            <a class="nav-link fw-semibold text-uppercase" href="#">About</a>
          </li>
        </ul>

        <div class="d-flex">
          <a href="#" class="nav-link me-3 fw-semibold text-uppercase">Reviews</a>
          <a href="#" class="nav-link me-3 fw-semibold text-uppercase">FAQ</a>
          <a href="#" class="nav-link fw-semibold text-uppercase">Cart (0)</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar-brand img {
  border-radius: 50%;
}
.navbar{
    background-color: var(--cream);
}
.nav-link {
  color: var(--primary-brown) !important;
  font-size: 14px;
  letter-spacing: 0.5px;
}

.nav-link:hover {
  color: var(--accent-orange) !important;
}
</style>
