<script setup lang="ts">
import { ref, onMounted, onUnmounted, watch } from 'vue'
import IconClose from './icons/IconClose.vue'

const isMenuOpen = ref(false)
const isHidden = ref(false)
const lastScrollY = ref(0)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

watch(isMenuOpen, (isOpen) => {
  if (isOpen) {
    document.body.style.overflow = 'hidden'
  } else {
    document.body.style.overflow = ''
  }
})

const handleScroll = () => {
  const currentScrollY = window.scrollY
  if (lastScrollY.value < currentScrollY && currentScrollY > 100) {
    isHidden.value = true
  } else {
    isHidden.value = false
  }
  lastScrollY.value = currentScrollY
}

onMounted(() => {
  lastScrollY.value = window.scrollY
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  document.body.style.overflow = ''
})
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-light py-0" :class="{ 'navbar-hidden': isHidden }">
    <div class="container nav-container">
      <!-- Mobile Header -->
      <div class="d-lg-none d-flex justify-content-between w-100 align-items-center">
        <!-- Mobile: Burger Menu -->
        <button class="navbar-toggler" type="button" @click="toggleMenu">
          <IconClose v-if="isMenuOpen" />
          <span v-else class="navbar-toggler-icon"></span>
        </button>

        <!-- Mobile: Centered Brand -->
        <a class="navbar-brand" href="#">
          <img
            src="../assets/images/logo.svg"
            alt="Amashwamshwam Logo"
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
              <a class="nav-link text-uppercase" href="#">Shop</a>
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
    </div>

    <!-- Mobile Menu Overlay -->
    <div class="mobile-menu-overlay" :class="{ show: isMenuOpen }" @click.self="toggleMenu">
      <div class="mobile-menu-card" :class="{ show: isMenuOpen }">
        <ul class="navbar-nav">
          <li class="nav-item"><a class="nav-link text-uppercase" href="#">Shop</a></li>
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
  position: sticky;
  top: 0;
  width: 100%;
  z-index: 1020;
  transition: transform 0.3s ease-in-out;
}

.navbar-hidden {
  transform: translateY(-100%);
}

.nav-container {
  display: flex;
  align-items: center;
  width: 100%;
}

.navbar-brand img {
  height: 5rem;
}

.nav-link {
  font-family: 'DK Frozen Memory', sans-serif;
  color: #e50102 !important;
  font-size: 1.3rem;
  letter-spacing: 1px;
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
}

/* Mobile styles */
@media (max-width: 991.98px) {
  .nav-container {
    flex-wrap: wrap;
  }
  .navbar-brand {
    font-size: 1.25rem;
  }
  .navbar-toggler {
    border: none;
    z-index: 1051; /* Ensure it's above the overlay */
  }

  .mobile-menu-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s ease, visibility 0.3s ease;
    z-index: 1040;
  }

  .mobile-menu-overlay.show {
    opacity: 1;
    visibility: visible;
  }

  .mobile-menu-card {
    position: absolute;
    bottom: -100%;
    left: 0;
    width: 100%;
    background-color: var(--cream);
    border-top-left-radius: 20px;
    border-top-right-radius: 20px;
    padding: 2rem;
    transition: bottom 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    box-shadow: 0 -5px 15px rgba(0,0,0,0.1);
  }

  .mobile-menu-card.show {
    bottom: 10px;
  }

  .mobile-menu-card .navbar-nav {
    align-items: flex-start;
  }
  
  .mobile-menu-card .nav-item {
    width: 100%;
    text-align: left;
    padding: 0.5rem 0;
  }
}
</style>
