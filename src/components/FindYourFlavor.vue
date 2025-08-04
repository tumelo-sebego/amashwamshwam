<script setup lang="ts">
import chilliProduct from '../assets/images/chilli_product.jpg'
import cheeseProduct from '../assets/images/cheese_product.jpg'
import comboProduct from '../assets/images/combo_product.jpg'
import purpleBg from '../assets/images/purple_bg.jpg'
const flavors = [
  {
    name: 'SWEET CHILLI FLAVOR',
    price: '5.00',
    quantity: '150g',
    count: 1,
    image: chilliProduct,
  },
  {
    name: 'CHEESE FLAVOR',
    price: '5.00',
    quantity: '150g',
    count: 1,
    image: cheeseProduct,
  },
  {
    name: 'SNACK COMBO',
    price: '10.00',
    count: 2,
    quantity: '150g',
    image: comboProduct,
  },
]
</script>

<template>
  <section class="section-spacing bg-cream">
    <div class="container">
      <div class="flavor-container py-5" :style="{ backgroundImage: `url(${purpleBg})` }">
        <div class="row mb-5">
          <div class="col-12 text-center">
            <h2 class="display-4 mb-3 title">PICK YOUR FLAVOR</h2>
          </div>
        </div>

        <div class="flavor-scroll-wrapper">
          <div class="row gx-4 flex-nowrap flex-md-wrap justify-content-md-center">
            <div v-for="flavor in flavors" :key="flavor.name" class="col-10 col-md-4 col-lg-3">
              <div class="flavor-card rounded-4 overflow-hidden shadow-lg">
                <div class="flavor-image-container">
                  <img :src="flavor.image" :alt="flavor.name" class="img-fluid" />
                </div>
                <div class="flavor-details">
                  <div class="d-flex justify-content-between">
                    <span class="product-name">{{ flavor.name }}</span>
                    <span class="product-price fw-bold">R{{ flavor.price }}</span>
                  </div>
                  <div class="product-quantity text-muted d-flex justify-content-between">
                    <span class="product-quantity">{{ flavor.count }} PACKET</span>
                    <span class="product-quantity">{{ flavor.quantity }}</span>
                  </div>
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
.flavor-container {
  background-color: #754bad;
  border-radius: 25px;
  background-size: cover;
  background-position: center;
}

.flavor-card {
  display: flex;
  flex-direction: column;
  height: 400px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background-color: white;
}

.title {
  color: rgb(239, 189, 7);
}
.flavor-card {
  cursor: pointer;
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

@media (max-width: 767.98px) {
  .flavor-container {
    overflow-x: hidden;
  }

  .flavor-scroll-wrapper {
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    scrollbar-width: none; /* Firefox */
  }

  .flavor-scroll-wrapper::-webkit-scrollbar {
    display: none; /* Chrome, Safari, Opera */
  }

  .flavor-scroll-wrapper .row {
    padding-left: 1rem;
    padding-right: 1rem;
    margin-left: 0;
    margin-right: 0;
  }
}
</style>
