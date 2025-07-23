<script setup lang="ts">
const foodImages = [
  {
    src: 'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=200&h=200&fit=crop',
    alt: 'Teriyaki Jerky Bites',
    caption: 'TERIYAKI JERKY BITES',
  },
  {
    src: 'https://images.pexels.com/photos/1633525/pexels-photo-1633525.jpeg?w=200&h=200&fit=crop',
    alt: 'Peppered Jerky Beef',
    caption: 'PEPPERED JERKY BEEF',
  },
  {
    src: 'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=200&h=200&fit=crop',
    alt: 'Spicy Jalapeño Jerky',
    caption: 'SPICY JALAPEÑO JERKY',
  },
  {
    src: 'https://images.pexels.com/photos/1633525/pexels-photo-1633525.jpeg?w=200&h=200&fit=crop',
    alt: 'Smoky BBQ Jerky',
    caption: 'SMOKY BBQ JERKY',
  },
  {
    src: 'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=200&h=200&fit=crop',
    alt: 'Original Beef Jerky',
    caption: 'ORIGINAL BEEF JERKY',
  },
  {
    src: 'https://images.pexels.com/photos/1633525/pexels-photo-1633525.jpeg?w=200&h=200&fit=crop',
    alt: 'Premium Wild Jerky',
    caption: 'PREMIUM WILD JERKY',
  },
]
</script>

<template>
  <section class="bg-success text-white section-spacing position-relative grass-bg">
    <div class="container">
      <div class="row mb-5">
        <div class="col-lg-6">
          <h2 class="display-4 fw-bold mb-4">HOW WE MAKE DELICIOUS FOOD</h2>
          <p class="fs-5 mb-4">
            Our jerky is hand-marinated for the perfect balance of flavors, then air-dried to
            perfection. We use traditional methods combined with modern techniques to ensure the
            highest quality.
          </p>
        </div>
        <div class="col-lg-6 text-end">
          <div class="d-flex justify-content-end gap-3">
            <button
              class="btn btn-outline-light btn-sm rounded-circle"
              style="width: 40px; height: 40px"
            >
              ←
            </button>
            <button
              class="btn btn-outline-light btn-sm rounded-circle"
              style="width: 40px; height: 40px"
            >
              →
            </button>
          </div>
        </div>
      </div>

      <div class="row g-4">
        <div v-for="(image, index) in foodImages" :key="index" class="col-lg-2 col-md-4 col-sm-6">
          <div class="food-card position-relative">
            <div class="polaroid-frame bg-white p-3 shadow-lg transform-rotate">
              <img
                :src="image.src"
                :alt="image.alt"
                class="img-fluid rounded mb-2"
                style="width: 100%; height: 120px; object-fit: cover"
              />
              <div class="caption text-center text-dark">
                <small
                  class="fw-bold text-uppercase"
                  style="font-size: 10px; letter-spacing: 0.5px"
                >
                  {{ image.caption }}
                </small>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Decorative elements -->
    <div class="position-absolute bottom-0 end-0 me-5 mb-5">
      <div class="decorative-element">
        <span style="font-size: 60px; opacity: 0.3">🍖</span>
      </div>
    </div>
  </section>
</template>

<style scoped>
.food-card {
  transition: all 0.3s ease;
}

.food-card:hover {
  transform: translateY(-10px) scale(1.05);
}

.polaroid-frame {
  transform: rotate(-2deg);
  transition: all 0.3s ease;
  max-width: 160px;
  margin: 0 auto;
}

.food-card:nth-child(even) .polaroid-frame {
  transform: rotate(2deg);
}

.food-card:hover .polaroid-frame {
  transform: rotate(0deg) scale(1.1);
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3) !important;
}

.caption {
  min-height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.decorative-element {
  animation: bounce 2s ease-in-out infinite;
}

@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}
</style>
