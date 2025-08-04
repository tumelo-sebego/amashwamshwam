<script setup lang="ts">
import logoImage from '../assets/images/logo.svg'
import purpleBg from '../assets/images/purple_bg.jpg'
const footerLinks = {
  shop: ['Jerky Products', 'Gift & Rewards', 'Wild Jerky Collection'],
  help: ['Our Story', 'Tracking', 'Contact'],
  connect: ['Newsletter', 'Wholesale Inquiries', 'Join our Team'],
}

const socialLinks = [
  { icon: 'facebook', url: '#' },
  { icon: 'instagram', url: '#' },
  { icon: 'twitter', url: '#' },
]
</script>

<template>
  <footer class="text-white" :style="{ backgroundImage: `url(${purpleBg})` }">
    <!-- Main footer content -->
    <div class="section-spacing">
      <div class="container">
        <div class="row g-4">
          <!-- Logo and description -->
          <div class="col-lg-4 col-md-6 mb-4">
            <div class="footer-brand mb-4">
              <div class="d-flex align-items-center mb-3">
                <img :src="logoImage" alt="Wild Jerky" height="40" class="logo me-3" />
              </div>
              <p class="text-light opacity-75 mb-4">
                Premium quality jerky made from grass-fed beef with no artificial preservatives.
                Fuel your adventures with our high-protein, delicious snacks.
              </p>

              <!-- Newsletter signup -->
              <div class="newsletter-signup">
                <h6 class="fw-bold text-uppercase mb-3">Stay Updated</h6>
                <div class="input-group">
                  <input
                    type="email"
                    class="form-control bg-transparent border-light text-white"
                    placeholder="Enter your email"
                  />
                  <button class="btn btn-primary" type="button">Subscribe →</button>
                </div>
              </div>
            </div>
          </div>

          <!-- Shop links -->
          <div class="col-lg-2 col-md-3 col-sm-6">
            <h6 class="fw-bold text-uppercase mb-4">Shop</h6>
            <ul class="list-unstyled">
              <li v-for="link in footerLinks.shop" :key="link" class="mb-2">
                <a href="#" class="text-light opacity-75 text-decoration-none hover-link">
                  {{ link }}
                </a>
              </li>
            </ul>
          </div>

          <!-- Help links -->
          <div class="col-lg-2 col-md-3 col-sm-6">
            <h6 class="fw-bold text-uppercase mb-4">Help</h6>
            <ul class="list-unstyled">
              <li v-for="link in footerLinks.help" :key="link" class="mb-2">
                <a href="#" class="text-light opacity-75 text-decoration-none hover-link">
                  {{ link }}
                </a>
              </li>
            </ul>
          </div>

          <!-- Connect links -->
          <div class="col-lg-2 col-md-3 col-sm-6">
            <h6 class="fw-bold text-uppercase mb-4">Connect</h6>
            <ul class="list-unstyled">
              <li v-for="link in footerLinks.connect" :key="link" class="mb-2">
                <a href="#" class="text-light opacity-75 text-decoration-none hover-link">
                  {{ link }}
                </a>
              </li>
            </ul>
          </div>

          <!-- Contact info -->
          <div class="col-lg-2 col-md-3 col-sm-6">
            <h6 class="fw-bold text-uppercase mb-4">Contact</h6>
            <div class="contact-info">
              <div class="mb-3">
                <small class="text-light opacity-75 d-block">Phone</small>
                <a href="tel:+1234567890" class="text-white text-decoration-none fw-semibold">
                  +1 (234) 567-890
                </a>
              </div>
              <div class="mb-3">
                <small class="text-light opacity-75 d-block">Email</small>
                <a
                  href="mailto:hello@wildjerky.com"
                  class="text-white text-decoration-none fw-semibold"
                >
                  hello@wildjerky.com
                </a>
              </div>

              <!-- Social links -->
              <div class="social-links mt-4">
                <h6 class="fw-bold text-uppercase mb-3" style="font-size: 12px">Follow Us</h6>
                <div class="d-flex gap-3">
                  <a
                    v-for="social in socialLinks"
                    :key="social.icon"
                    :href="social.url"
                    class="social-link text-white"
                  >
                    <div
                      class="social-icon rounded-circle d-flex align-items-center justify-content-center"
                    >
                      <svg
                        v-if="social.icon === 'facebook'"
                        width="16"
                        height="16"
                        fill="currentColor"
                        viewBox="0 0 24 24"
                      >
                        <path
                          d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
                        />
                      </svg>
                      <svg
                        v-else-if="social.icon === 'instagram'"
                        width="16"
                        height="16"
                        fill="currentColor"
                        viewBox="0 0 24 24"
                      >
                        <path
                          d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"
                        />
                      </svg>
                      <svg
                        v-else-if="social.icon === 'twitter'"
                        width="16"
                        height="16"
                        fill="currentColor"
                        viewBox="0 0 24 24"
                      >
                        <path
                          d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"
                        />
                      </svg>
                    </div>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer bottom -->
    <div class="footer-bottom py-4 border-top border-secondary">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-md-6">
            <p class="mb-0 text-light opacity-75">© 2025 Amashwamshwam. All rights reserved.</p>
          </div>
          <div class="col-md-6 text-md-end">
            <div class="d-flex justify-content-md-end gap-4 mt-3 mt-md-0">
              <p class="mb-0 text-light opacity-75">
                Designed by
                <a
                  href="https://tumeloGraphicStudio.netlify.app"
                  class="text-light opacity-75 text-decoration-none hover-link"
                  >tumeloGraphicStudio</a
                >
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
footer {
  background-color: rebeccapurple;
  background-size: cover;
  background-position: center;
}

.hover-link {
  transition: all 0.3s ease;
}

.hover-link:hover {
  opacity: 1 !important;
  color: var(--accent-orange) !important;
  transform: translateX(5px);
}

.social-icon {
  width: 36px;
  height: 36px;
  background: rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

.social-link:hover .social-icon {
  background: var(--accent-orange);
  transform: translateY(-3px);
}

.newsletter-signup .form-control::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.newsletter-signup .form-control:focus {
  background-color: rgba(255, 255, 255, 0.1);
  border-color: var(--accent-orange);
  color: white;
  box-shadow: 0 0 0 0.2rem rgba(231, 126, 34, 0.25);
}

.input-group .btn-primary {
  border-left: none;
}

.footer-bottom {
  background: rgba(0, 0, 0, 0.2);
}

.logo {
  width: 7rem;
  height: auto;
}

@media (max-width: 768px) {
  .social-links .d-flex {
    justify-content: center;
  }

  .text-md-end {
    text-align: center !important;
  }

  .justify-content-md-end {
    justify-content: center !important;
  }
}
</style>
