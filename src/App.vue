<script setup lang="ts">
import SpotlightCard from './components/SpotlightCard/SpotlightCard.vue'
</script>

<template>
  <div class="mx-auto max-w-xl p-8">
    <h1 class="mb-8 text-2xl font-bold">Vue Bits Demo</h1>

    <SpotlightCard class="bg-neutral-900 border-neutral-700 text-white" spotlightColor="rgba(59, 130, 246, 0.5)">
      <h2 class="mb-2 text-lg font-semibold">SpotlightCard</h2>
      <p class="opacity-80">マウスを動かすとスポットライトエフェクトが表示されます</p>
    </SpotlightCard>
  </div>
</template>
