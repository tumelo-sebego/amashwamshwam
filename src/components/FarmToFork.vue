<script setup lang="ts"></script>

<template>
  <section class="bg-cream section-spacing position-relative">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6 mb-5 mb-lg-0">
          <h2 class="display-4 fw-bold text-primary-brown mb-4">
            FROM <span class="text-warning">FARM</span> TO
            <span class="text-primary-brown">FORK,</span>
            WE CONNECT TO OUR ROOTS
          </h2>
          <p class="fs-5 text-muted mb-4">
            We source all of our beef from family-owned farms across the heartland of America,
            ensuring the highest quality of farming practices and the best quality.
          </p>
          <button class="btn btn-primary px-4 py-3 text-uppercase fw-bold">Read More →</button>
        </div>

        <div class="col-lg-6">
          <div class="farm-image position-relative">
            <img
              src="https://images.pexels.com/photos/422218/pexels-photo-422218.jpeg?w=600&h=400&fit=crop"
              alt="Farm with cattle"
              class="img-fluid rounded-4 shadow-lg w-100"
              style="height: 400px; object-fit: cover"
            />

            <!-- Overlay with cattle silhouettes -->
            <div class="cattle-overlay position-absolute bottom-0 start-0 w-100">
              <div class="d-flex justify-content-center align-items-end pb-4">
                <div class="cattle-silhouette me-3" style="font-size: 40px; opacity: 0.8">🐄</div>
                <div class="cattle-silhouette me-3" style="font-size: 35px; opacity: 0.7">🐄</div>
                <div class="cattle-silhouette me-3" style="font-size: 45px; opacity: 0.9">🐄</div>
                <div class="cattle-silhouette me-3" style="font-size: 30px; opacity: 0.6">🐄</div>
                <div class="cattle-silhouette" style="font-size: 38px; opacity: 0.8">🐄</div>
              </div>
            </div>

            <!-- Mountain background -->
            <div
              class="mountain-bg position-absolute top-0 start-0 w-100 h-100 rounded-4 overflow-hidden"
              style="z-index: -1"
            >
              <div class="mountain-silhouette"></div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Grass decoration at bottom -->
    <div class="grass-decoration position-absolute bottom-0 start-0 w-100">
      <svg viewBox="0 0 100 10" class="w-100" style="height: 40px">
        <path
          d="M0,10 Q10,0 20,10 Q30,0 40,10 Q50,0 60,10 Q70,0 80,10 Q90,0 100,10 L100,10 L0,10 Z"
          fill="#27ae60"
          opacity="0.8"
        />
      </svg>
    </div>
  </section>
</template>

<style scoped>
.farm-image {
  position: relative;
  overflow: hidden;
}

.cattle-overlay {
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.3));
  border-radius: 0 0 1rem 1rem;
}

.cattle-silhouette {
  animation: graze 4s ease-in-out infinite;
  filter: sepia(1) hue-rotate(30deg) brightness(0.5);
}

.cattle-silhouette:nth-child(2n) {
  animation-delay: -1s;
}

.cattle-silhouette:nth-child(3n) {
  animation-delay: -2s;
}

@keyframes graze {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-5px);
  }
}

.mountain-silhouette {
  width: 100%;
  height: 100%;
  background: linear-gradient(
    to bottom,
    rgba(52, 152, 219, 0.3) 0%,
    rgba(46, 204, 113, 0.2) 40%,
    rgba(241, 196, 15, 0.1) 70%,
    transparent 100%
  );
}

.grass-decoration {
  pointer-events: none;
}

.btn-primary:hover {
  transform: translateX(5px);
  transition: transform 0.3s ease;
}
</style>
