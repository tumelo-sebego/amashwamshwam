<script setup lang="ts">
const flavors = [
  {
    name: 'CHEESE FLAVOR',
    price: '28.95',
    quantity: '150g',
    image:
      'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=300&h=400&fit=crop',
  },
  {
    name: 'SWEET CHILLY FLAVOR',
    price: '28.95',
    quantity: '150g',
    image:
      'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=300&h=400&fit=crop',
  },
  {
    name: 'SALT & VINEGAR',
    price: '28.95',
    quantity: '150g',
    image: 'https.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=300&h=400&fit=crop',
  },
]
</script>

<template>
  <section class="section-spacing bg-cream">
    <div class="container">
      <div class="row mb-5">
        <div class="col-12 text-center">
          <h2 class="display-4 mb-3 title">PICK YOUR FLAVOR</h2>
        </div>
      </div>

      <div class="row justify-content-center g-4">
        <div v-for="flavor in flavors" :key="flavor.name" class="col-md-3 col-sm-12">
          <div class="flavor-card h-100 rounded-4 overflow-hidden shadow-lg">
            <div class="flavor-image-container">
              <img :src="flavor.image" :alt="flavor.name" class="img-fluid" />
            </div>
            <div class="flavor-details">
              <div class="d-flex justify-content-between">
                <span class="product-name">{{ flavor.name }}</span>
                <span class="product-price fw-bold">R{{ flavor.price }}</span>
              </div>
              <div class="product-quantity text-muted">
                {{ flavor.quantity }}
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
  display: flex;
  flex-direction: column;
  height: 400px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background-color: white;
}

.title {
  color: #e50102;
}
.flavor-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2) !important;
}

.flavor-image-container {
  height: 80%;
  overflow: hidden;
}

.flavor-image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.flavor-details {
  height: 20%;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  font-family: 'Cooper Hewitt Bold', sans-serif;
  letter-spacing: 0.5px;
}

.product-name {
  font-weight: 600;
  font-size: 0.9rem;
}

.product-price {
  font-size: 0.9rem;
}

.product-quantity {
  font-size: 0.8rem;
}
</style>
