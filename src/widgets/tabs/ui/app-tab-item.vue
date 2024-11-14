<template>
  <li
    @click="emits('changeTab')"
    class="px-2 pb-4 border-b-2 border-transparent text-base text-[#666] inline-block cursor-pointer"
    :class="{ '!border-[#5A8CF1] !text-[#5A8CF1] font-medium': isActive }"
  >
    {{ tab.text }}
  </li>
</template>

<script setup lang="ts">
import type { Tab } from '../model'

interface Props {
  tab: Tab
  isActive: boolean
}

defineProps<Props>()

const emits = defineEmits<{
  (e: 'changeTab'): void
}>()
</script>
