<script setup lang="ts">
const benefits = [
  'PERFECT DIPPING',
  'GUILT-FREE SNACK',
  'NUTRITIONAL',
  'HIGH PROTEIN',
  'HIGH FIBERS',
  'LOW FAT',
  'MELTS IN MOUTH',
]
</script>

<template>
  <section class="bg-dark-wood text-white section-spacing position-relative overflow-hidden">
    <!-- Background decorative elements -->
    <div class="position-absolute top-0 start-0 w-100 h-100 opacity-10">
      <div
        class="decoration-circle bg-success position-absolute"
        style="width: 200px; height: 200px; top: 20%; left: 10%; border-radius: 50%"
      ></div>
      <div
        class="decoration-circle bg-warning position-absolute"
        style="width: 150px; height: 150px; top: 60%; right: 15%; border-radius: 50%"
      ></div>
      <div
        class="decoration-circle bg-danger position-absolute"
        style="width: 100px; height: 100px; top: 10%; right: 25%; border-radius: 50%"
      ></div>
    </div>

    <div class="container position-relative">
      <div class="row align-items-center">
        <div class="col-lg-8">
          <div class="benefits-grid">
            <div class="row g-3">
              <div v-for="benefit in benefits" :key="benefit" class="col-6 col-md-4 col-lg-3">
                <div class="benefit-tag text-center">
                  <div class="benefit-image mb-2">
                    <img
                      src="https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=60&h=60&fit=crop"
                      alt="Jerky"
                      class="rounded-circle"
                      style="width: 50px; height: 50px; object-fit: cover"
                    />
                  </div>
                  <div class="benefit-text">
                    <span
                      class="fw-bold text-uppercase"
                      style="font-size: 11px; letter-spacing: 0.5px"
                    >
                      {{ benefit }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="col-lg-4 text-center">
          <div class="product-showcase">
            <div class="product-stack position-relative">
              <img
                src="https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=200&h=300&fit=crop"
                alt="Wild Jerky Pack"
                class="main-product img-fluid rounded-3 shadow-lg"
                style="max-width: 200px"
              />
              <img
                src="https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=200&h=300&fit=crop"
                alt="Wild Jerky Pack"
                class="product-shadow position-absolute img-fluid rounded-3"
                style="max-width: 200px; top: 10px; left: -10px; opacity: 0.7; z-index: -1"
              />
            </div>

            <div class="mt-4">
              <div
                class="price-display bg-warning text-dark px-4 py-2 rounded-pill d-inline-block fw-bold"
              >
                $28.95 | SHOP NOW →
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.benefit-tag {
  padding: 15px 10px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.benefit-tag:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateY(-2px);
}

.product-showcase {
  animation: float 3s ease-in-out infinite;
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.price-display {
  font-size: 14px;
  letter-spacing: 1px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.price-display:hover {
  background-color: #f1c40f !important;
  transform: scale(1.05);
}

.decoration-circle {
  animation: pulse 4s ease-in-out infinite;
}

@keyframes pulse {
  0%,
  100% {
    opacity: 0.1;
    transform: scale(1);
  }
  50% {
    opacity: 0.2;
    transform: scale(1.1);
  }
}
</style>
