<template>
  <div class="scroll-banner" :style="{ maxHeight: `${maxHeight}px` }">
    <div class="scroll-content" :style="{ animationDuration: animationSpeed }">
      <span v-for="(word, index) in extendedWords" :key="index" class="scroll-word">{{
        word
      }}</span>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue'

const props = withDefaults(
  defineProps<{
    maxHeight?: number
    words?: string[]
    speed?: 'slow' | 'medium' | 'fast'
  }>(),
  {
    maxHeight: 50,
    words: () => [
      'Hand-Crafted',
      'Locally-Sourced',
      'Fresh-Ingredients',
      'Community-Focused',
      'Sustainable-Farming',
    ],
    speed: 'medium',
  }
)

const extendedWords = computed(() => {
  const baseWords =
    props.words.length > 0
      ? props.words
      : [
          'Hand-Crafted',
          'Locally-Sourced',
          'Fresh-Ingredients',
          'Community-Focused',
          'Sustainable-Farming',
        ]
  // To create a seamless loop, we repeat the words enough times to fill the banner.
  // The animation will then scroll through one of these repeated blocks.
  const repeatedWords = Array(20).fill(baseWords).flat()
  return repeatedWords
})

const animationSpeed = computed(() => {
  const wordCount = extendedWords.value.length
  let baseDuration

  switch (props.speed) {
    case 'slow':
      baseDuration = 50 // Slower speed
      break
    case 'fast':
      baseDuration = 10 // Faster speed
      break
    case 'medium':
    default:
      baseDuration = 20 // Medium speed
      break
  }

  // Adjust the animation duration based on the number of words
  const dynamicDuration = (wordCount * baseDuration) / 10
  return `${dynamicDuration}s`
})
</script>

<style scoped>
.scroll-banner {
  overflow: hidden;
  width: 100%;
  display: flex;
  align-items: center;
  font-family: 'DK Frozen Memory', sans-serif;
}

.scroll-content {
  display: flex;
  flex-shrink: 0;
  animation-name: scroll;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  min-width: 100%;
}

.scroll-word {
  padding: 0 2rem;
  font-size: 1.2rem;
  white-space: nowrap;
  color: #333;
}

@keyframes scroll {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-50%);
  }
}
</style>
