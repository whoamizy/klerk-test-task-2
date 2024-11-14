<template>
  <nav>
    <ul class="flex">
      <li v-for="(item, idx) in items" :key="idx" class="flex items-center">
        <span v-if="idx > 0" class="inline-block mx-2">
          <img src="/icons/arrow.svg" alt="arrow" />
        </span>
        <a
          :href="item.path"
          class="text-[13px]/[16px] text-[#999] border-b border-[#E6EDFF] hover:text-[#5A8CF1]"
        >
          {{ item.text }}
        </a>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Crumb {
  text: string
  path: string
}

const items = ref<Crumb[]>([
  {
    text: 'Главная',
    path: '/',
  },
  {
    text: 'Рассылки',
    path: '/',
  },
  {
    text: 'Хлебные крошки',
    path: '/',
  },
])
</script>
