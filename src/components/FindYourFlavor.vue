<script setup lang="ts">
const flavors = [
  {
    name: 'CHEESE FLAVOR',
    price: '28.95',
    image:
      'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=300&h=400&fit=crop',
    bgColor: '#4a3728',
    description: 'Rich teriyaki flavor with a hint of salt',
  },
  {
    name: 'SWEET CHILLY FLAVOR',
    price: '28.95',
    image:
      'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=300&h=400&fit=crop',
    bgColor: '#e67e22',
    description: 'Spicy jalapeño with smoky undertones',
  },
]
</script>

<template>
  <section class="section-spacing bg-cream grass-bg">
    <div class="container">
      <div class="row mb-5">
        <div class="col-12 text-center">
          <h2 class="display-4 text-primary-brown mb-3">PICK YOUR FLAVOR</h2>
        </div>
      </div>

      <div class="row justify-content-center g-4">
        <div v-for="flavor in flavors" :key="flavor.name" class="col-lg-6 col-md-6 col-sm-12">
          <div class="flavor-card h-100 rounded-4 overflow-hidden shadow-lg position-relative">
            <div
              class="card-bg h-100 p-4 d-flex flex-column justify-content-between text-center text-white"
              :style="{ backgroundColor: flavor.bgColor }"
            >
              <div>
                <div class="product-image mb-4">
                  <img
                    :src="flavor.image"
                    :alt="flavor.name"
                    class="img-fluid rounded-3 shadow"
                  />
                </div>

                <h4 class="fw-bold mb-3 text-white">{{ flavor.name }}</h4>
                <p class="small mb-4 opacity-90">{{ flavor.description }}</p>
              </div>

              <div>
                <div class="price-tag mb-3">
                  <span class="fs-4 fw-bold">${{ flavor.price }}</span>
                  <span class="small opacity-75 ms-2">ADD TO CART</span>
                </div>

                <button class="btn btn-outline-light btn-sm w-100 py-2 rounded-3">
                  ADD TO CART
                </button>
              </div>

              <!-- Corner decoration -->
              <div class="corner-decoration position-absolute top-0 end-0 m-3">
                <div
                  class="bg-white rounded-circle d-flex align-items-center justify-content-center"
                  style="width: 30px; height: 30px"
                >
                  <span class="text-dark fw-bold" style="font-size: 12px">★</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.flavor-card {
  min-height: 400px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.flavor-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2) !important;
}

.product-image img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

@media (max-width: 767.98px) {
  .product-image img {
    height: auto;
    aspect-ratio: 1 / 1;
  }
}

.price-tag {
  border-top: 1px solid rgba(255, 255, 255, 0.3);
  padding-top: 1rem;
}

.corner-decoration {
  opacity: 0.8;
}

.btn-outline-light:hover {
  background-color: white;
  color: var(--primary-brown);
  border-color: white;
}
</style>
