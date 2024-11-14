<template>
  <ul class="flex gap-4">
    <AppTabItem
      v-for="(item, idx) in items"
      :key="idx"
      :tab="item"
      :is-active="activeTab === idx"
      @change-tab="changeTab(idx)"
    />
  </ul>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { Tab } from '../model'
import AppTabItem from './app-tab-item.vue'

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

const changeTab = (idx: number) => {
  activeTab.value = idx
}
</script>
