<script setup lang="ts">
import ScrollBanner from './components/ScrollBanner.vue'
import NavHeader from './components/NavHeader.vue'
import HeroCarousel from './components/HeroCarousel.vue'
import FindYourFlavor from './components/FindYourFlavor.vue'
import BenefitCards from './components/BenefitCards.vue'
import RecipeSection from './components/RecipeSection.vue'
import DeliciousFood from './components/DeliciousFood.vue'
import FarmToFork from './components/FarmToFork.vue'
import InstagramSection from './components/InstagramSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <div>
    <ScrollBanner :words="['CRUNCHY', 'SWAMSWAM', 'MNANDI']" bannerColor="#efbd07" />
    <NavHeader />
    <HeroCarousel />
    <FindYourFlavor />
    <ScrollBanner
      :words="['HIGH PROTEIN', 'LOW FAT', 'NON GMO', 'FIBER RICH', 'NUTRIOUS', 'HEALTHY SNACK']"
    />
    <BenefitCards />
    <RecipeSection />
    <DeliciousFood />
    <FarmToFork />
    <InstagramSection />
    <FooterSection />
  </div>
</template>

<style scoped></style>
