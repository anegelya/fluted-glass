<template>
  <div class="max-w-screen overflow-x-hidden py-24">
    <p class="text-[18vw] leading-none break-words break-all">
      TOI-3235 b. Mass (Mj) - 0.665±0.025, Radius (Rj) - 1.017±0.044, Period (days) 2.59261842±0.00000041, Semi-major axis (AU) - 0.02709±0.00046, Temp. (K) - 604±19.
    </p>
    <p class="text-[18vw] leading-none break-words break-all">
      TOI-4127 b. Mass (Mj) - 2.30±0.11, Radius (Rj) - 1.096+0.039−0.032, Period (days) 56.39879±0.00010, Semi-major axis (AU) - 0.3081+0.0055−0.0058, Temp. (K) - 605.1+9.6−8.2.
    </p>
  </div>
  <div class="fixed top-0 left-0 right-0 bottom-0 w-full h-svh flex justify-center items-center z-10">
    <div class="w-full max-w-xl h-[10em] p-4">
      <FlutedGlass :type="isCross ? 'cross' : 'fluted'">
        <div class="flex items-center space-x-2">
          <Switch
            id="cross-fluted-glass"
            v-model:checked="isCross"
          />
          <Label for="cross-fluted-glass">
            Cross Reed
          </Label>
        </div>
      </FlutedGlass>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { Switch } from './components/ui/switch'
import { Label } from './components/ui/label'
import FlutedGlass from './components/FlutedGlass.vue'

const isCross = ref(false)

</script>
