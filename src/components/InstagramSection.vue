<script setup lang="ts">
const instagramPosts = [
  {
    src: 'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=250&h=250&fit=crop',
    alt: 'Jerky on wooden board',
    username: '@wildjerkyfan',
  },
  {
    src: 'https://images.pexels.com/photos/1633525/pexels-photo-1633525.jpeg?w=250&h=250&fit=crop',
    alt: 'Spiced jerky close-up',
    username: '@foodlover',
  },
  {
    src: 'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?w=250&h=250&fit=crop',
    alt: 'Jerky with herbs',
    username: '@healthfitness',
  },
  {
    src: 'https://images.pexels.com/photos/1633525/pexels-photo-1633525.jpeg?w=250&h=250&fit=crop',
    alt: 'Premium jerky selection',
    username: '@premiumeats',
  },
]
</script>

<template>
  <section class="bg-white section-spacing">
    <div class="container">
      <div class="row mb-5">
        <div class="col-md-8">
          <h2 class="display-5 fw-bold text-primary-brown mb-3">FOLLOW OUR INSTAGRAM</h2>
          <p class="text-muted fs-5">Get exclusive glimpses, recipe ideas and delicious snaps!</p>
        </div>
        <div class="col-md-4 text-md-end">
          <div class="instagram-handle d-flex align-items-center justify-content-md-end">
            <div class="instagram-icon me-3">
              <div
                class="rounded-circle bg-gradient d-flex align-items-center justify-content-center"
                style="
                  width: 50px;
                  height: 50px;
                  background: linear-gradient(
                    45deg,
                    #f09433 0%,
                    #e6683c 25%,
                    #dc2743 50%,
                    #cc2366 75%,
                    #bc1888 100%
                  );
                "
              >
                <svg width="24" height="24" fill="white" viewBox="0 0 24 24">
                  <path
                    d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"
                  />
                </svg>
              </div>
            </div>
            <div>
              <h5 class="fw-bold text-primary-brown mb-0">WILD JERKY</h5>
              <small class="text-muted">@wildjerky</small>
            </div>
          </div>
        </div>
      </div>

      <div class="row g-4">
        <div v-for="(post, index) in instagramPosts" :key="index" class="col-lg-3 col-md-6">
          <div class="instagram-post position-relative overflow-hidden rounded-4 shadow">
            <img
              :src="post.src"
              :alt="post.alt"
              class="img-fluid w-100"
              style="height: 250px; object-fit: cover"
            />

            <!-- Instagram overlay -->
            <div
              class="instagram-overlay position-absolute top-0 start-0 w-100 h-100 d-flex align-items-center justify-content-center opacity-0"
            >
              <div class="text-center text-white">
                <div class="instagram-icon-overlay mb-2">
                  <svg width="32" height="32" fill="white" viewBox="0 0 24 24">
                    <path
                      d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"
                    />
                  </svg>
                </div>
                <small class="fw-semibold">{{ post.username }}</small>
              </div>
            </div>

            <!-- Like button -->
            <div class="position-absolute top-0 end-0 m-3">
              <button class="btn btn-light btn-sm rounded-circle p-2 opacity-75">
                <svg width="16" height="16" fill="red" viewBox="0 0 24 24">
                  <path
                    d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"
                  />
                </svg>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.instagram-post {
  transition: all 0.3s ease;
  cursor: pointer;
}

.instagram-post:hover {
  transform: translateY(-5px);
}

.instagram-post:hover .instagram-overlay {
  opacity: 1 !important;
  background: rgba(0, 0, 0, 0.7);
  transition: all 0.3s ease;
}

.instagram-overlay {
  transition: all 0.3s ease;
}

.instagram-icon-overlay {
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

.btn-light:hover {
  background-color: white !important;
  transform: scale(1.1);
}
</style>
