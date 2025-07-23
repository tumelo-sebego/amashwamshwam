<script setup lang="ts">
const features = ['HIGH PROTEIN', 'LOW FAT', 'NON GMO', 'FIBER RICH', 'NUTRITIOUS', 'HEALTHY SNACK']
</script>

<template>
  <section class="py-4 bg-success text-white">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-12">
          <div class="d-flex justify-content-center align-items-center flex-wrap gap-4">
            <div
              v-for="(feature, index) in features"
              :key="feature"
              class="d-flex align-items-center"
            >
              <div class="feature-icon me-2">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z" />
                </svg>
              </div>
              <span class="fw-semibold text-uppercase" style="font-size: 14px; letter-spacing: 1px">
                {{ feature }}
              </span>
              <div
                v-if="index < features.length - 1"
                class="separator ms-4"
                style="width: 2px; height: 20px; background: rgba(255, 255, 255, 0.3)"
              ></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.feature-icon {
  width: 24px;
  height: 24px;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media (max-width: 768px) {
  .separator {
    display: none;
  }
}
</style>
