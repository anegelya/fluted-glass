<template>
  <div class="relative w-full h-full rounded-2xl cursor-pointer transition-all duration-[50ms] ease-in active:scale-[0.98]">
    <div class="h-full w-full backdrop-blur-md rounded-2xl overflow-hidden bg-stone-200/10 shadow-xl">
    </div>

    <div class="grooves-v absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden bg-zinc-400/10 backdrop-blur-xl"></div>
    <div
      v-if="type === 'cross'"
      class="grooves-h absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden bg-stone-400/10 backdrop-blur-xl">
    </div>

    <div class="diffusion-v absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden bg-indigo-300/10"></div>

    <div
      class="absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden border-[1px] border-stone-300/20 z-20 flex justify-center items-center">
      <slot />
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps, withDefaults } from 'vue'

type FlutedGlassType = 'fluted' | 'cross'

export interface FlutedGlassProps {
  type: FlutedGlassType,
}

withDefaults(defineProps<FlutedGlassProps>(), {
  type: 'fluted',
})

</script>

<style scoped>
.grooves-v {
  mask-image: repeating-linear-gradient(to right,
      black 0px,
      black 1px,
      transparent 3px,
      transparent 6px);
}
.grooves-h {
  mask-image: repeating-linear-gradient(to bottom,
      black 0px,
      black 1px,
      transparent 3px,
      transparent 6px);
}
.diffusion-v {
  mask-image: repeating-linear-gradient(to right,
      transparent 0px,
      transparent 3px,
      black 4px,
      black 5px,
      transparent 6px);
}
</style>
