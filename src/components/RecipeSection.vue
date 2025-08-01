<template>
  <section class="recipe-section bg-cream">
    <div class="container">
      <div class="d-md-none text-justify-center">
        <h4 class="display-4 mb-3 title">Join the Movement. Become a Reseller</h4>
        <p>
          Start your own business with just R175. Sell AmaShwamShwam snacks and keep the profit. No
          boss, no limits just vibes.
        </p>
      </div>
      <div class="row justify-content-center">
        <div class="col-md-5 mb-3 mt-4">
          <div class="image-wrapper">
            <img :src="logoImage" alt="Logo" class="logo-overlay" />
            <div class="recipe-image-container">
              <img :src="recipeImage" alt="Recipe Image" class="recipe-image" />
            </div>
          </div>
        </div>
        <div class="col-md-5">
          <div class="recipe-content">
            <div class="d-none d-md-block">
              <h4 class="display-4 mb-3 title">Join the Movement. Become a Reseller</h4>
              <p>
                Start your own business with just R175. Sell AmaShwamShwam snacks and keep the
                profit. No boss, no limits, just vibes.
              </p>
            </div>
            <div class="recipe-highlight">
              <h5 class="fw-bold">How the Program Works</h5>
              <p>
                The AmaShwamShwam Reseller Program is designed to help you kickstart your own
                micro-business with minimal upfront costs and maximum flexibility.
              </p>
              <ul class="list-unstyled mb-0">
                <li>
                  <strong>1. Buy a Starter Pack –</strong> Get started with just
                  <strong>R175</strong>. Each starter pack includes <strong>60 packets</strong> of
                  AmaShwamShwam snacks.
                </li>
                <li>
                  <strong>2. Sell Anywhere –</strong> Resell the snacks in your community, at
                  school, work, events, or even from your backpack. No shop needed, just hustle and
                  passion.
                </li>
                <li>
                  <strong>3. Keep the Profit –</strong> Sell each packet for R5–R7. You decide the
                  price. The more you sell, the more you earn—it’s that simple.
                </li>
                <li>
                  <strong>4. Get Support –</strong> Early resellers get
                  <strong>free merch</strong> (T-shirts, caps, bags), brand exposure on our social
                  media, and tips to help you grow your sales.
                </li>
              </ul>
            </div>
            <div class="text-center btn-container">
              <button class="btn-custom"><span>JOIN THEN PROGRAM</span></button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import recipeImage from '../assets/images/member.jpg'
import logoImage from '../assets/images/logo.svg'
</script>
<style scoped>
.recipe-section {
  padding: 60px 0;
}

.bg-cream {
  background-color: #fdf5e6;
}

.image-wrapper {
  position: relative;
  height: 104%;
}

.recipe-image-container {
  border-radius: 25px;
  overflow: hidden;
  height: 100%;
}

.logo-overlay {
  position: absolute;
  top: -40px;
  left: 0rem;
  width: 8rem;
  height: auto;
  z-index: 1;
}

@media (max-width: 767.98px) {
  .recipe-image-container {
    height: auto;
  }

  .logo-overlay {
    position: absolute;
    top: -40px;
    left: 13rem;
    width: 8rem;
    height: auto;
    z-index: 1;
  }

  .btn-container {
    justify-content: center !important;
  }
}

.recipe-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.recipe-section h4 {
  font-family: 'DK Frozen Memory', sans-serif;
  color: #e50102;
  margin-bottom: 1rem;
}

.recipe-section p {
  font-family: 'Cooper Hewitt', sans-serif;
  color: #e50102;
  margin-bottom: 1.5rem;
  text-align: justify;
}

.recipe-highlight {
  background-color: #ffc801;
  border-radius: 25px;
  padding: 1.5rem;
  margin-bottom: 1.5rem;
  color: #e50102;
  font-family: 'Cooper Hewitt Bold';
  text-align: justify;
}

.recipe-highlight h5 {
  font-family: 'Cooper Hewitt Bold', sans-serif;
}

.text-red {
  color: #e50102;
}

.recipe-buttons {
  display: flex;
  gap: 1rem;
}

.btn-white-round {
  background-color: white;
  border: 4px solid #e50102;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  cursor: pointer;
}

.btn-container {
  display: flex;
  justify-content: start;
}
</style>
