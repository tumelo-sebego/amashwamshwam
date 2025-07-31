<template>
  <section class="recipe-section bg-cream">
    <div class="container">
      <div class="d-md-none text-justify-center">
        <h4 class="display-4 mb-3 title">Mix and Match Recipe</h4>
        <p>
          Unleash your inner chef with our versatile beef jerky. Crumble it over salads, toss it in
          stir-fries, or add it to your favorite trail mix for a protein-packed crunch. The
          possibilities are as endless as your imagination.
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
        <div class="col-md-4">
          <div class="recipe-content">
            <div class="d-none d-md-block">
              <h4 class="display-4 mb-3 title">Mix and Match Recipe</h4>
              <p>
                Unleash your inner chef with our versatile beef jerky. Crumble it over salads, toss
                it in stir-fries, or add it to your favorite trail mix for a protein-packed crunch.
                The possibilities are as endless as your imagination.
              </p>
            </div>
            <div class="recipe-highlight">
              <p class="text-red">
                Our jerky is the secret ingredient you never knew you needed. Elevate your everyday
                meals with a burst of savory flavor and satisfying texture.
              </p>
            </div>
            <div class="recipe-buttons">
              <button class="btn-white-round">&lt;</button>
              <button class="btn-white-round">&gt;</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import recipeImage from '../assets/images/recipe1.jpg'
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
}

.recipe-highlight {
  background-color: #fde26f;
  border-radius: 25px;
  padding: 1.5rem;
  margin-bottom: 1.5rem;
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
</style>
