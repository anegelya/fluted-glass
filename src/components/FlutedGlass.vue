<template>
  <div class="relative w-full h-full rounded-2xl">
    <div class="h-full w-full backdrop-blur-md rounded-2xl overflow-hidden bg-stone-200/10 shadow-xl">
    </div>
    <div class="absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden bg-stone-400/20 backdrop-blur-xl fluted-glass"></div>
    <div
      class="absolute h-full w-full top-0 left-0 right-0 bottom-0 rounded-2xl overflow-hidden border-[1px] border-stone-300/20 z-20 flex justify-center items-center">
      <slot />
    </div>
  </div>
</template>

<style>
.fluted-glass {
  mask-image: repeating-linear-gradient(to right,
      black 0px,
      black 1px,
      transparent 3px,
      transparent 6px);
}
</style>
