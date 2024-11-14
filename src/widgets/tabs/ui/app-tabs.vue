<template>
  <ul class="flex gap-4">
    <li
      v-for="(item, idx) in items"
      :key="idx"
      @click="changeTab(item, idx)"
      class="px-2 pb-4 border-b-2 border-transparent text-base text-[#666] inline-block cursor-pointer"
      :class="{ 'border-[#5A8CF1] !text-[#5A8CF1] font-medium': activeTab === idx }"
    >
      {{ item.text }}
    </li>
  </ul>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Tab {
  text: string
  path: string
}

const items = ref<Tab[]>([
  {
    text: 'Рассылки',
    path: '/',
  },
  {
    text: 'Соцсети',
    path: '/',
  },
  {
    text: 'Мессенджеры',
    path: '/',
  },
])

const activeTab = ref(0)

const changeTab = (tab: Tab, idx: number) => {
  activeTab.value = idx
  console.log('Go to:', tab.path)
}
</script>
