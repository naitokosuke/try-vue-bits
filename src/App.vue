<script setup lang="ts">
import {
  SpotlightCard,
  GradientText,
  AnimatedContent,
  Iridescence,
  GhostCursor,
} from './components/vue-bits'
</script>

<template>
  <div class="relative h-screen">
    <div class="absolute inset-0">
      <Iridescence :color="[0.2, 0.22, 0.95]" :speed="1.0" :amplitude="0.1" />
    </div>

    <GhostCursor color="#3438F2" />

    <div class="relative z-10 mx-auto max-w-xl p-8">
      <AnimatedContent :threshold="0">
        <GradientText
          text="Vue Bits Demo"
          class="text-4xl font-bold mb-8 rounded-none"
          :colors="['#3438F2', '#6366F1', '#3438F2']"
        />
      </AnimatedContent>

      <AnimatedContent :threshold="0" :delay="0.2">
        <SpotlightCard class="bg-neutral-900/80 border-neutral-700 text-white" spotlightColor="#3438F2">
          <h2 class="text-lg font-semibold">Interactive Components</h2>
        </SpotlightCard>
      </AnimatedContent>
    </div>
  </div>
</template>
