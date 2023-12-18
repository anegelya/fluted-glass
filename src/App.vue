<template>
  <div class="my-[20em]">
    <h1 class="text-[6em] leading-none mb-[2em]">TOI-<br>3235 b</h1>
    <img src="/planet.png" alt="TOI-3235 b" class="relative w-screen mb-[20em]">
  </div>
  <div class="fixed bottom-4 w-full h-[7em] p-4">
    <FlutedGlass>
      <CheckoutButton />
    </FlutedGlass>
  </div>
</template>

<script setup lang="ts">
import FlutedGlass from './components/FlutedGlass.vue'
import CheckoutButton from './components/CheckoutButton.vue'
</script>
