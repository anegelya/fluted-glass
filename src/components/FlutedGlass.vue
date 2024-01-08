<template>
  <div class="relative w-full h-full rounded-2xl cursor-pointer transition-all duration-75 ease-in active:scale-[0.98]">
    <div class="h-full w-full backdrop-blur-md rounded-2xl overflow-hidden bg-stone-200/10 shadow-xl">
    </div>

    <div
      class="absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden bg-zinc-400/10 backdrop-blur-xl"
      :style="groovesStyle">
    </div>

    <div class="absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden bg-indigo-300/10"
      :style="diffusionStyle">
    </div>

    <div
      class="absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden border-[1px] border-stone-300/20 z-20 flex justify-center items-center">
      <slot />
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed, withDefaults } from 'vue'

export type FlutedGlassType = 'fluted' | 'cross' | 'romb' | 'circle'

export interface FlutedGlassProps {
  type: FlutedGlassType,
  angle?: number,
}

const props = withDefaults(defineProps<FlutedGlassProps>(), {
  type: 'fluted',
})

function createGroove(angle: number) {
  if (props.type === 'circle') {
    return `repeating-radial-gradient(circle at 50%,
      black 0px,
      black 1px,
      transparent 3px,
      transparent 6px)`
  }
  return `repeating-linear-gradient(${angle}deg,
      black 0px,
      black 1px,
      transparent 3px,
      transparent 6px)`
}

const groovesStyle = computed(() => {
  const groovesAngle = props.angle ?? (props.type === 'romb' ? 45 : 90)

  const grooves = [
    createGroove(groovesAngle)
  ]

  if (props.type !== 'fluted') {
    grooves.push(createGroove(groovesAngle + 90))
  }

  return {
    maskImage: grooves.join(', ')
  }
})

function createDiffusion(angle: number) {
  if (props.type === 'circle') {
    return `repeating-radial-gradient(circle at 50%,
      transparent 0px,
      transparent 3px,
      black 4px,
      black 5px,
      transparent 6px)`
  }
  return `repeating-linear-gradient(${angle}deg,
      transparent 0px,
      transparent 3px,
      black 4px,
      black 5px,
      transparent 6px)`
}

const diffusionStyle = computed(() => {
  const angle = props.angle ?? (props.type === 'romb' ? 45 : 90)

  return {
    maskImage: createDiffusion(angle)
  }
})

</script>
