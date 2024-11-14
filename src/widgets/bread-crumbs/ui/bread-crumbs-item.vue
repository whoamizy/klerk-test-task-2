<template>
  <li class="flex items-center">
    <span v-if="showArrow" class="inline-block mx-2">
      <img src="/icons/arrow.svg" alt="arrow" />
    </span>
    <a
      :href="crumb.path"
      class="text-[13px]/[16px] text-[#999] border-b border-[#E6EDFF] hover:text-[#5A8CF1]"
    >
      {{ crumb.text }}
    </a>
  </li>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import type { Crumb } from '../model'

interface Props {
  index: number
  crumb: Crumb
}

const props = defineProps<Props>()

const showArrow = computed(() => {
  return props.index > 0
})
</script>
