<template>
  <div class="max-w-screen overflow-x-hidden py-24 text-[#ffd68a]">
    <p class="text-[18vw] leading-none break-words break-all">
      TOI-3235 b. Mass (<i>M</i><sub>j</sub>) - 0.665±0.025, Radius (<i>R</i><sub>j</sub>) - 1.017±0.044, Period (days) 2.59261842±0.00000041, Semi-major axis (AU) - 0.02709±0.00046, Temp. (K) - 604±19.
    </p>
    <p class="text-[18vw] leading-none break-words break-all">
      TOI-4127 b. Mass (<i>M</i><sub>j</sub>) - 2.30±0.11, Radius (<i>R</i><sub>j</sub>) - 1.096+0.039−0.032, Period (days) 56.39879±0.00010, Semi-major axis (AU) - 0.3081<sup>+0.0055</sup><sub>−0.0058</sub>, Temp. (K) - 605.1<sup>+9.6</sup><sub>−8.2</sub>.
    </p>
  </div>
  <div class="fixed top-0 left-0 right-0 bottom-0 w-full h-svh flex justify-center items-center z-10">
    <div class="w-full max-w-xl h-[10em] p-4">
      <FlutedGlass :type="glassType">
        <div class="flex items-center space-x-2">
          <Select v-model:model-value="glassType">
            <SelectTrigger>
              <SelectValue placeholder="Select glass type" />
            </SelectTrigger>
            <SelectContent>
              <SelectItem
                v-for="t in types"
                :key="t"
                :value="t">
                {{ t }}
              </SelectItem>
            </SelectContent>
          </Select>
        </div>
      </FlutedGlass>
    </div>
  </div>

  <div class="fixed left-4 bottom-4 z-10">
    <div class="flex justify-center text-white mt-8">
      <Button
        as="a"
        href="https://github.com/anegelya/fluted-glass"
        size="sm">
        <Icon icon="line-md:github-twotone" class="w-4 h-4 me-1" />
        github
      </Button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, Ref } from 'vue'
import { Icon } from '@iconify/vue'
import { Button } from './components/ui/button'
import {
  Select,
  SelectContent,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from '@/components/ui/select'
import FlutedGlass, { FlutedGlassType } from './components/FlutedGlass.vue'

const types: FlutedGlassType[] = [
  'fluted',
  'cross',
  'romb',
  'circle',
]

const glassType: Ref<FlutedGlassType | undefined> = ref(undefined)

</script>
