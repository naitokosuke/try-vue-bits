<script setup lang="ts">
import { SpotlightCard, GradientText } from './components/vue-bits'
</script>

<template>
  <div class="mx-auto max-w-xl p-8">
    <h1 class="mb-8 text-2xl font-bold">Vue Bits Demo</h1>

    <GradientText
      text="Gradient Text"
      class="text-4xl font-bold mb-8"
      :colors="['#3438F2', '#6366F1', '#3438F2']"
    />

    <SpotlightCard class="bg-neutral-900 border-neutral-700 text-white" spotlightColor="#3438F2">
      <h2 class="mb-2 text-lg font-semibold">SpotlightCard</h2>
      <p class="opacity-80">マウスを動かすとスポットライトエフェクトが表示されます</p>
    </SpotlightCard>
  </div>
</template>
