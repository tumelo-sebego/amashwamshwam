<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-light py-3">
    <div class="container nav-container">
      <!-- Mobile Header -->
      <div class="d-lg-none d-flex justify-content-between w-100 align-items-center">
        <!-- Mobile: Burger Menu -->
        <button class="navbar-toggler" type="button" @click="toggleMenu">
          <span class="navbar-toggler-icon"></span>
        </button>

        <!-- Mobile: Centered Brand -->
        <a class="navbar-brand" href="#">
          <img
            src="../assets/images/logo.svg"
            alt="Wild Jerky"
            height="40"
            class="d-inline-block align-text-top me-2"
          />
        </a>

        <!-- Mobile: Icons -->
        <div class="d-flex align-items-center">
          <a href="#" class="nav-link">
            <!-- Placeholder for search icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="20"
              height="20"
              fill="currentColor"
              class="bi bi-search"
              viewBox="0 0 16 16"
            >
              <path
                d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"
              />
            </svg>
          </a>
          <a href="#" class="nav-link">
            <!-- Placeholder for cart icon -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="20"
              height="20"
              fill="currentColor"
              class="bi bi-cart"
              viewBox="0 0 16 16"
            >
              <path
                d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .491.592l-1.5 7A.5.5 0 0 1 13 11H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5zM3.102 4l1.313 6h8.17l1.313-6H3.102zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2zm7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"
              />
            </svg>
          </a>
        </div>
      </div>

      <!-- Desktop Header -->
      <div class="d-none d-lg-flex justify-content-between w-100 align-items-center">
        <!-- Desktop: Left Links -->
        <div class="nav-left">
          <ul class="navbar-nav flex-row">
            <li class="nav-item me-3">
              <a class="nav-link text-uppercase" href="#">Shop Jerky</a>
            </li>
            <li class="nav-item me-3">
              <a class="nav-link text-uppercase" href="#">Recipes</a>
            </li>
            <li class="nav-item">
              <a class="nav-link text-uppercase" href="#">About</a>
            </li>
          </ul>
        </div>

        <!-- Desktop: Centered Brand -->
        <a class="navbar-brand nav-center" href="#">
          <img
            src="../assets/images/logo.svg"
            height="40"
            class="d-inline-block align-text-top me-2"
          />
        </a>

        <!-- Desktop: Right Links -->
        <div class="nav-right">
          <ul class="navbar-nav flex-row">
            <li class="nav-item me-3">
              <a href="#" class="nav-link text-uppercase">Reviews</a>
            </li>
            <li class="nav-item me-3">
              <a href="#" class="nav-link text-uppercase">FAQ</a>
            </li>
            <li class="nav-item">
              <a href="#" class="nav-link text-uppercase">Cart (0)</a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Mobile Menu (collapsible) -->
      <div class="collapse navbar-collapse d-lg-none" :class="{ show: isMenuOpen }">
        <ul class="navbar-nav text-center w-100 mt-3">
          <li class="nav-item"><a class="nav-link text-uppercase" href="#">Shop Jerky</a></li>
          <li class="nav-item"><a class="nav-link text-uppercase" href="#">Recipes</a></li>
          <li class="nav-item"><a class="nav-link text-uppercase" href="#">About</a></li>
          <li class="nav-item"><a href="#" class="nav-link text-uppercase">Reviews</a></li>
          <li class="nav-item"><a href="#" class="nav-link text-uppercase">FAQ</a></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  background-color: var(--cream);
}

.nav-container {
  display: flex;
  align-items: center;
  width: 100%;
}

.navbar-brand img {
  height: 6rem;
}

.nav-link {
  color: #e50102 !important;
  font-size: 14px;
  letter-spacing: 0.5px;
  font-weight: 800;
}

.nav-link:hover {
  color: var(--accent-orange) !important;
}

/* Desktop styles */
@media (min-width: 992px) {
  .nav-left,
  .nav-right {
    flex: 1;
  }
  .nav-right {
    display: flex;
    justify-content: flex-end;
  }
  .nav-center {
    flex-shrink: 0;
  }
  .navbar-expand-lg .navbar-collapse {
    display: none !important;
    flex-basis: auto;
  }
}

/* Mobile styles */
@media (max-width: 991.98px) {
  .nav-container {
    flex-wrap: wrap;
  }
  .navbar-brand {
    font-size: 1.25rem; /* Adjust brand size for mobile */
  }
  .navbar-toggler {
    border: none;
  }
  .navbar-collapse {
    flex-basis: 100%;
  }
}
</style>
